<template>
  <div>
    <div class="d-flex justify-content-end">
      <p>ようこそ{{ userName }}さん</p>
    </div>
    <div class="mb-3">
      <router-link to="/mypage/attendance/detail">
        一覧へ戻る
      </router-link>
    </div>
    <h3 class="mb-3">{{ setToday }}の勤務登録</h3>
    <p class="p-attendanceStatus">
      {{ status }}
    </p>
    <div class="d-flex justify-content-between mb-5">
      <router-link to="">
        {{ setYesterday }}
      </router-link>
      <router-link to="">
        {{ setTomorrow }}
      </router-link>
    </div>
    <div class="form-group">
      <div class="p-form__select">
        <label for="selectForm">出勤場所</label>
        <select id="selectForm" class="form-control">
          <option>オフィス</option>
          <option>リモート</option>
        </select>
      </div>
      <div class="d-flex justify-content-between">
        <div class="p-form__select">
          <lavel>出勤時刻</lavel>
          <input type="time" value="10:00" class="form-control" >
        </div>
        <div class="p-form__select">
          <lavel>退勤時刻</lavel>
          <input type="time" value="19:00" class="form-control" >
        </div>
      </div>
      <div class="d-flex justify-content-between">
        <div class="p-form__select">
          <lavel>勤務時間</lavel>
          <input type="time" value="09:00" class="form-control" >
        </div>
        <div class="p-form__select">
          <lavel>休憩時間</lavel>
          <input type="time" value="01:00" class="form-control" >
        </div>
      </div>
    </div>
    <div class="form-group">
      <label for="textarea">日報</label>
      <textarea id="textarea" class="form-control" rows="5" />
    </div>
    <div v-if="!addField" class="form-group d-flex align-items-end mb-5">
      <div class="p-form__select__timeTagName">
        <lavel>時間タグ</lavel>
        <input class="form-control" >
      </div>
      <div class="p-form__select__timeTag">
        <input type="time" value="00:00" class="form-control" >
      </div>
      <div>
        <button type="button" class="btn btn-primary" @click="addTimeTag">
          追加
        </button>
      </div>
      <div>
        <button
          type="button"
          class="btn btn-danger p-btn_delete"
          @click="addTimeTag"
        >
          削除
        </button>
      </div>
    </div>
    <div v-if="addField" class="form-group d-flex align-items-end mb-5">
      <div class="p-form__select__timeTagName">
        <input class="form-control" >
      </div>
      <div class="p-form__select__timeTag">
        <input type="time" value="00:00" class="form-control" >
      </div>
      <div>
        <button type="button" class="btn btn-primary" @click="addTimeTag">
          追加
        </button>
      </div>
    </div>
    <div class="d-flex justify-content-end">
      <router-link to="/mypage/attendance/detail" class="btn btn-primary">
        確定
      </router-link>
    </div>
  </div>
</template>
<script>
import moment from "moment"
export default {
  layout: "default",
  head() {
    return {
      title: "勤務登録"
    }
  },
  data() {
    return {
      userName: "ユーザー名",
      status: "出勤",
      addField: false,
      form_text: ""
    }
  },
  computed: {
    setToday() {
      return moment().format("YYYY-MM-DD")
    },
    setYesterday() {
      return moment()
        .subtract(1, "days")
        .format("YYYY-MM-DD")
    },
    setTomorrow() {
      return moment()
        .add(1, "days")
        .format("YYYY-MM-DD")
    },
    methods: {
      addTimeTag() {
        this.form_text = ""
        this.addField = true
      }
    }
  }
}
</script>
<style lang="scss" scoped>
.p-form__select {
  width: 50%;
  padding: 5px;
}
.p-attendanceStatus {
  font-size: 18px;
}
.p-form__select__timeTagName {
  width: 30%;
  padding-right: 10px;
}
.p-form__select__timeTag {
  width: 20%;
  padding-right: 10px;
}
.p-btn_delete {
  margin-left: 10px;
}
</style>

<template>
  <div>
    <div class="mb-3">
      <router-link to="/login">
        マイページへ
      </router-link>
    </div>
    <h3 class="mb-3">{{ setToday }}の勤務記録</h3>
    <div class="d-flex mb-3">
      <div class="p-toAttendanceList">
        <router-link to="">
          勤務一覧
        </router-link>
      </div>
      <router-link to="/mypage/attendance/summary">
        サマリ
      </router-link>
    </div>
    <h2 class="mb-2">
      勤怠
    </h2>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        出勤日
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ date_work }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        休暇取得
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ date_holiday }}</span>
        days
      </p>
    </div>
    <h2 class="mb-2">
      勤務詳細
    </h2>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        出勤日
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ date_work }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        勤務時間
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ hour_work }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        休憩時間
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ hour_breakTime }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        一日平均勤務時間
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ hour_averageWork }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        一日平均休憩時間
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ hour_averageBreakTime }}</span>
        days
      </p>
    </div>
    <h2 class="mb-2">
      休暇明細
    </h2>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        休暇取得
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ date_holiday }}</span>
        days
      </p>
    </div>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        有給取得
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ date_holiday }}</span>
        days
      </p>
    </div>
    <h2 class="mb-2">
      勤務タグ集計
    </h2>
    <div class="d-flex justify-content-between align-items-end mb-3 p-listItem">
      <p class="mb-0">
        {{ tag_work }}
      </p>
      <p class="mb-0">
        <span class="p-workingTime">{{ tag_workHour }}</span>
        days
      </p>
    </div>
  </div>
</template>
<script>
import moment from "moment"
export default {
  layout: "default",
  data() {
    return {
      date: "2019-09",
      date_work: "8",
      date_holiday: "3",
      hour_work: "60",
      hour_breakTime: "8",
      hour_averageWork: "8",
      hour_averageBreakTime: "8",
      date_nationalHoliday: "2",
      tag_work: "web制作",
      tag_workHour: "10"
    }
  },
  computed: {
    setToday() {
      return moment().format("YYYY-MM-DD")
    }
  }
}
</script>
<style lang="scss" scoped>
.p-listItem {
  border-bottom: 1px solid #c1c5ce;
}
.p-toAttendanceList {
  padding-right: 30px;
}
.p-workingTime {
  font-size: 30px;
  padding-right: 5px;
}
</style>

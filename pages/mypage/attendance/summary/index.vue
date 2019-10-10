<template>
  <div>
    <div class="mb-3">
      <router-link to="/login">
        マイページへ
      </router-link>
    </div>
    <h3 class="mb-3">{{ setToday }}の勤務記録</h3>
    <div class="d-flex mb-3">
      <div class=" p-toAttendanceList">
        <router-link to="/mypage/attendance/detail">
          勤務一覧
        </router-link>
      </div>
      <router-link to="">
        サマリ
      </router-link>
    </div>
    <table class="table table-hover">
      <colgroup>
        <col style="width:15%">
        <col style="width:10%">
        <col style="width:10%">
        <col style="width:10%">
        <col style="width:10%">
        <col style="width:10%">
        <col style="width:10%">
      </colgroup>
      <thead>
        <tr>
          <th>日付</th>
          <th>種別</th>
          <th>勤務場所</th>
          <th>出勤時刻</th>
          <th>退勤時刻</th>
          <th>勤務時間</th>
          <th>休憩時間</th>
        </tr>
      </thead>
      <tr
        v-for="(workRecordItem, index) in workRecordList"
        :key = "index"
        @click=""
      >
        <td>{{ workRecordItem.date }}</td>
        <td>{{ workRecordItem.type }}</td>
        <td>{{ workRecordItem.place }}</td>
        <td>{{ workRecordItem.startTime }}</td>
        <td>{{ workRecordItem.endTime }}</td>
        <td>{{ workRecordItem.totalTime }}</td>
        <td>{{ workRecordItem.breakTime }}</td>
      </tr>
    </table>
  </div>
</template>
<script>
import moment from "moment"
export default {
  data() {
    return {
      workRecordList: [
        {
          date: "2019-10-01(月)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-02(火)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-03(水)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-04(木)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-05(金)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-06(土)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
        {
          date: "2019-10-07(日)",
          type: "出勤",
          place: "オフィス",
          startTime: "10:30",
          endTime: "19:00",
          totalTime: "08:30",
          breakTime: "01:00"
        },
      ]
    }
  },
  computed: {
    setToday() {
      return moment().format("YYYY-MM-DD")
    }
  }
}
</script>
<style lang="scss">
.p-toAttendanceList {
  padding-right: 30px;
}
</style>


<template>
    <div>
        <h1>月別出勤一覧</h1>
        <table class="table table-hover">
            <colgroup>
                <col style="width:50%">
                <col style="width:50%">
            </colgroup>
            <thead>
            <tr>
                <th>年</th>
                <th>月</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(atendanceItem,index) in attendanceList" :key="index" @click="$router.push('/login')">
                <td>{{ atendanceItem.year }}</td>
                <td>{{ atendanceItem.month }}</td>
            </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
    export default {
        layout: "default",
        head() {
            return {
                title: '月別出勤一覧'
            }
        },
        data() {
            return {
                attendanceList: [
                    {
                        year: '2019',
                        month: '9'
                    },
                    {
                        year: '2019',
                        month: '10'
                    },
                    {
                        year: '2019',
                        month: '11'
                    },
                    {
                        year: '2019',
                        month: '12'
                    },
                ]
            }
        }
    }
</script>
<style lang="scss" scoped>
</style>
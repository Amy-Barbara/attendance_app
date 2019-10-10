<template>
  <div>
    <div class="p-loginForm">
      <form>
        <div class="form-group">
          <lavel>
            ID
          </lavel>
          <input type="text" class="form-control" >
        </div>
      </form>
      <form>
        <div class="form-group">
          <lavel>
            パスワード
          </lavel>
          <input type="text" class="form-control" >
        </div>
      </form>
      <div class="text-center">
        <router-link to="/mypage/attendance/register/create">
          <button type="button" class="btn btn-primary">
            ログイン
          </button>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  layout: "default"
}
</script>
<style lang="scss" scoped>
.p-loginForm {
  width: 340px;
  margin: auto;
}
</style>

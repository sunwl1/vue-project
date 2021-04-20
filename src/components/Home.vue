<template>
  <div id="Login">
    <section>
      <article id="login_container">
        <div class="form_area">
          <form id="login_form">
            <div class="label">로그인</div>
            <div>
              <input
                id="user_id"
                class="login_input"
                type="text"
                placeholder="ID"
              />
              <input
                id="user_pwd"
                class="login_input"
                type="password"
                placeholder="Password"
              />
            </div>
            <button class="btn_small" type="button">회원가입</button>
            <div>
              <button id="login_btn" class="btn" type="submit">로그인</button>
            </div>
          </form>
        </div>
      </article>
      <article id="register_container">
        <div class="register_box">
          <form id="register_form">
            <div class="label">회원가입</div>
            <div>
              <input
                id="register_id"
                class="login_input"
                type="text"
                placeholder="ID"
              />
              <input
                id="register_pwd"
                class="login_input"
                type="password"
                placeholder="Password"
              />
              <select id="user_role">
                <option value="Admin">Admin</option>
                <option value="User">User</option>
              </select>
              <button class="btn_small" type="button">취소</button>
            </div>
            <div>
              <button class="btn" type="submit">회원가입</button>
            </div>
          </form>
        </div>
      </article>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user_id: "",
      user_pwd: "",
      isLogin: true,
      isRegister: false,
      register_id: "",
      register_pwd: "",
      register_role: "Admin",
    };
  },
  methods: {
    loginSubmit: function () {
      console.log("로그인");
      this.$router.push("/");
    },
    login: function () {
      this.isLogin = true;
      this.isRegister = false;
    },
    register: function () {
      this.isLogin = false;
      this.isRegister = true;
    },
    registerSubmit: function () {
      console.log("회원가입 완료");
      this.login();
    },
    registBtn: function () {
      console.log("회원가입");
      this.register();
    },
    cancelBtn: function () {
      this.login();
    },
  },
};
</script>

<style scoped>
</style>

<template>
  <div id="loginwrapper">
    <h1 id="logintitle">로그인</h1>
  </div>
  <div class="btnwrapper">
    <div>
      <button type="button" id="nonmemberbtn" v-on:click="nonmemberLogin">
        비로그인 이용
      </button>
    </div>
    <div>
      <button type="button" id="kakaobtn" v-on:click="kakaoLogin">
        <img
          src="../../../src/assets/img/main/kakaoImg.png"
          width="30"
          height="30"
          style="margin-right: 2%"
        />
        <!-- <a
          href="https://kauth.kakao.com/oauth/authorize?client_id=8147c85395148371709b2199642f9108&redirect_uri=http://localhost:3000/login/kakao&state=kakao&response_type=code"
          style="text-decoration: none; color: white"
          >카카오톡 로그인</a
        > -->
        <a
          href="https://kauth.kakao.com/oauth/authorize?client_id=8147c85395148371709b2199642f9108&redirect_uri=https://j8a109.p.ssafy.io/login/kakao&state=kakao&response_type=code"
          style="text-decoration: none; color: white"
          >카카오톡 로그인</a
        >
      </button>
    </div>
  </div>
</template>

<script>
import router from "@/router";

// const BASE_URL = "http://localhost:8080"

export default {
  name: "LoginComp",
  setup() {},
  methods: {
    nonmemberLogin() {
      sessionStorage.setItem("pk", 0);
      sessionStorage.setItem("token", null);
      router.push({ name: "storyCreate" });
    },
  },
  created() {},
};
</script>

<style scoped>
#loginwrapper {
  height: 30vh;
  display: flex;
  align-items: center;
}

#logintitle {
  font-family: "Dovemayo_gothic";
  font-size: 3.5rem;
  font-weight: bold;
  color: #4d455d;
}

.btnwrapper {
  height: 20vh;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

#nonmemberbtn {
  width: 20vw;
  height: 7vh;
  background-color: rgb(189, 189, 189);
  border-radius: 25px;
  color: white;
  font-family: "Dovemayo_gothic";
  font-size: 1.7rem;
  font-weight: bold;
  border: 0px solid white;
  display: flex;
  justify-content: center;
  align-items: center;
}
#kakaobtn {
  width: 20vw;
  height: 7vh;
  font-family: "Dovemayo_gothic";
  background-color: #4d455d;
  border-radius: 25px;
  color: white;
  font-size: 1.7rem;
  font-weight: bold;
  border: 0px solid white;
  display: flex;
  justify-content: center;
  align-items: center;
}

#nonmemberbtn:hover {
  background-color:#4d455d;
}

#kakaobtn:hover{
  background-color: #FEE500;
}
</style>

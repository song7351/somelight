<template>
  <div>
    <button id="backbtn" v-on:click="$router.go(-1)">뒤로</button>
    <div id="content">
      <div id="bulbWrapper" v-if="result === 2">
        <img src="@/assets/img/result/fix_green.png" alt="" />
      </div>
      <div id="bulbWrapper" v-else-if="result === 1">
        <img src="@/assets/img/result/fix_black.png" alt="" />
      </div>
      <div id="bulbWrapper" v-else-if="result === 0">
        <img src="@/assets/img/result/fix_red.png" alt="" />
      </div>
      <div id="contentdetail">
        {{ content }}
      </div>
    </div>
    <delete-comp v-if="loginflag" />
  </div>
</template>

<script>
import DeleteComp from "./mystory/DeleteComp.vue";

export default {
  data() {
    return {
      // articleId: this.$store.state.article.result,
    };
  },
  methods: {},
  created() {},
  components: {
    DeleteComp,
  },
  props: ["loginflag"],
  computed: {
    result() {
      return this.$store.state.article.result;
    },
    content() {
      return this.$store.state.article.content;
    },
  },
};
</script>

<style scoped>
#content {
  width: 30vw;
  height: 50vh;
  border-radius: 20px;
  /* background-color: #F5E9CF;  */
  background-color: white;
  /* background-color: black; */
  opacity: 0.8;
  /* margin-right: 1vw; */
  margin-top: 5vh;
  box-shadow: 3px 3px 3px rgb(216, 216, 216);
  display: flex;
  justify-content: center;
  align-items: flex-end;
  /* overflow: scroll; */
  /* overflow-x: hidden; */
  position: relative;
}

#content::-webkit-scrollbar {
  width: 10px;
}

/* #contentdetail {
  margin-top: 20vh;
  width: 30vw;
  height: 50vh;
  margin-left: 2vw;
  margin-right: 2vw;
  line-height: 2rem;
  font-size: 1.5rem;
  display: -webkit-box;
  word-break: break-all;
  resize: none;
} */
#contentdetail {
  width: 90%;
  height: 80%;
  line-height: 2rem;
  font-size: 1.5rem;
  overflow: auto;
  /* display: -webkit-box; */
  word-break: break-all;
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE 10+ */
}
#contentdetail::-webkit-scrollbar {
  width: 0 !important;
}
#resultWrapper {
  width: 25%;
  min-height: 50%;
  /* height: auto; */
  margin-left: 3%;
  margin-top: 3%;
  margin-bottom: 3%;
  /* background-color: rgba(255, 251, 251, 100%); */
  border-radius: 20px;
  /* border: 1px solid rgba(233, 217, 217, 100%); */
  /* box-shadow: 8px 4px 4px rgba(0, 0, 0, 25%); */
  position: absolute;
  z-index: 0;
  display: flex;
  justify-content: center;
  /* align-items: center; */
}
#backbtn {
  font-family: "Dovemayo_gothic";
  width: 5vw;
  color: white;
  font-weight: bold;
  font-size: 1.2rem;
  height: 5vh;
  border-radius: 30px;
  border: 0px solid black;
  background-color: #4d455d;
  box-shadow: 3px 3px 3px rgb(187, 187, 187);
  margin-top: 7vh;
}

#backbtn:hover {
  background-color: black;
}

#bulbWrapper {
  border-radius: 100%;
  width: 25%;
  height: 30%;
  background-color: white;
  position: absolute;
  top: -18%;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0px solid rgba(190, 176, 176, 100%);
  background-color: rgba(255, 251, 251, 100%);
  border-radius: 100%;
  border: 1px solid rgba(233, 217, 217, 100%);
  box-shadow: 2px 2px 2px rgb(187, 187, 187);
}

/* #bulbWrapper {
  border-radius: 100%;
  width: 30%;
  height: 30%;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: -15%;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
  border: 0px solid rgba(190, 176, 176, 100%);
  background-color: rgba(255, 251, 251, 100%);
  border-radius: 100%;
  border: 1px solid rgba(233, 217, 217, 100%);
  box-shadow: 2px 2px 2px rgb(187, 187, 187);
} */

#bulbWrapper > img {
  height: 80%;
  /* width: 90%; */
  /* border-radius: 100%; */
}
</style>

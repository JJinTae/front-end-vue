<!-- 컴포넌트 UI 정의 -->
<template>
  <div class="card">
    <div class="card-header">
      Exam01EventHandling
    </div>
    <div class="card-body">
      <h6>[Event Handler]</h6>
      <button class="btn btn-info btn-sm mr-2" v-on:click="handleBtn1">버튼1</button>
      <button class="btn btn-info btn-sm mr-2" @click="handleBtn2('Vue is good', $event)" name="btn2">버튼2</button>
      <button class="btn btn-info btn-sm mr-2" @click="handleBtn2('Vue is good', $event)" name="btn3">버튼3</button>
      <hr>
      <a href="/" @click.prevent="handleLink()">링크</a>

      <hr>

      <form @submit.prevent="handleSubmit">
        <div class="d-flex align-items-center justify-content-center">
          <input type="submit" value="제출" class="btn btn-info btn-sm mr-2"/>
          <button class="btn btn-info btn-sm mr-2">제출</button>
          <input type="image" :src="require(`@/assets/logo.png`)" height="30"/>
        </div>
      </form>

      <hr>

      <button class="btn btn-info btn-sm mr-2" @click.ctrl="handleBtn3" name="btn3">Ctrl + Click</button>

    </div>
  </div>
</template>

<script>
export default {
  // 컴포넌트의 대표이름(devtools에 나오는 이름)
  name: "Exam01EventHandling",
  // 추가하고 싶은 컴포넌트 등록(import something from "/path")
  components: {},
  // 컴포넌트 데이터 정의
  data() {
    return {};
  },
  // 컴포넌트 메소드 정의
  methods: {
    handleBtn1() {
      console.log("handleBtn1() 실행");
    },
    handleBtn2(arg, event) {
      console.log("arg : ", arg);
      console.log("event : ", event);
      if(event.target.name === "btn2") {
        console.log("btn2가 클릭됨");
      } else if (event.target.name === "btn3") {
        console.log("btn3가 클릭됨");
      }
    },
    handleLink(event) {
      event.preventDefault();
    },
    handleSubmit() {
      console.log("AJAX 통신으로 폼 데이터 전송");
    },
    handleBtn3() {
      console.log("handleBtn3() 실행");
    },

  },
};
</script>

<!-- 컴포넌트 스타일 정의 -->
<style scoped>
</style>
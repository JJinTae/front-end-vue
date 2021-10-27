<!-- 컴포넌트 UI 정의 -->
<template>
  <div class="card">
    <div class="card-header">
        Exam05View
    </div>
    <div class="card-body">
        <h6>params(path variable)로 전달</h6>
        <ul>
            <li><router-link to="/menu01/exam06view/1">exam06View/1</router-link></li>
            <li><router-link v-bind:to="`/menu01/exam06view/${bno1}`">exam06View/3</router-link></li>
            <li><router-link :to="{path: `/menu01/exam06view/${bno2}`}">exam06view/5</router-link></li>
            <li><router-link :to="{name: 'menu01_exam06view', params: {bno:bno3}}">exam06view/7</router-link></li>
        </ul>
        <h6>정적 프롭 객체 전달</h6>
        <ul>
          <li><router-link to="/menu01/exam07view">exam07View/1</router-link></li>
        </ul>

        <h6>쿼리 스트링으로 전달</h6>
        <ul>
          <li><router-link to="/menu01/exam08view?kind=freeboard&color=blue">exam08View?kind=freeboard&color=blue</router-link></li>
          <li><router-link :to="`/menu01/exam08view?kind=${kind1}&color=${color1}`">exam08View?kind=freeboard&color=blue</router-link></li>
          <li><router-link :to="{path: `/menu01/exam08view?kind=${kind2}&color=${color2}`}">exam08View?kind=album&color=red</router-link></li>
          <li><router-link :to="{name: 'menu01_exam08view', query:{kind:kind3, color:color3}}">exam08View?kind=qa&color=yellow</router-link></li>
        </ul>
    </div>
  </div>
</template>

<script>
export default {
  // 컴포넌트의 대표이름(devtools에 나오는 이름)
  name: "Exam05View",
  // 추가하고 싶은 컴포넌트 등록(import something from "/path")
  components: {},
  // 컴포넌트 데이터 정의
  data() { 
    // data() 와 같이 곧바로 함수로 사용해도 된다. 또는 data: () => {}
    // data: () => ({bno1: 3, bno2: 5, bno3: 7}) 과 같이 return을 바로 할 수 도 있다.
    return {
        bno1: 3,
        bno2: 5,
        bno3: 7,
        kind1: "freeboard",
        color1: "blue",
        kind2: "album",
        color2: "red",
        kind3: "qa",
        color3: "yellow",
    };
  },
  // 컴포넌트 메소드 정의
  methods: {},
};
</script>

<!-- 컴포넌트 스타일 정의 -->
<style scoped>
</style>
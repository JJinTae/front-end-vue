<!-- 컴포넌트 UI 정의 -->
<template>
  <div class="card">
    <div class="card-header">
      Exam05ForRepeatBinding
    </div>
    <div class="card-body">
      <h6>범위 반복</h6>
      <span v-for="n in 6" :key="n" class="mr-2">
        <img :src="require(`@/assets/photos/photo${n}.jpg`)" height="100" v-if="n%2===0" >
      </span>

      <hr>

      <h6>배열 항목 반복</h6>
      <div>
        <span v-for="(photo, index) in photos" :key="index">
          <img :src="require(`@/assets/photos/${photo}`)" height="100" v-if="index<=2" >
        </span>
      </div>

      <hr>

      <h6>객체 배열 항목 반복</h6>
      <table class="table table-bordered">
        <thead>
          <tr>
            <th>No</th>
            <th>Title</th>
            <th>Writer</th>
            <th>Date</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="board in boards" :key="board.bno">
            <td>{{board.bno}}</td>
            <td>{{board.btitle}}</td>
            <td>{{board.bwriter}}</td>
            <td>{{board.bdate}}</td>
          </tr>
        </tbody>

      </table>

    </div>
  </div>
</template>

<script>
import boardData from "@/data/boardData"
import photoData from '@/data/photoData';

export default {
  // 컴포넌트의 대표이름(devtools에 나오는 이름)
  name: "Exam05ForRepeatBinding",
  // 추가하고 싶은 컴포넌트 등록(import something from "/path")
  components: {},
  // 컴포넌트 데이터 정의
  data() {
    return {
      photos : photoData.photos,
      boards : boardData.boards,
    };
  },
  // 컴포넌트 메소드 정의
  methods: {},
};
</script>

<!-- 컴포넌트 스타일 정의 -->
<style scoped>
</style>
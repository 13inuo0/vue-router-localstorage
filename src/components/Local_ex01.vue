<template>
  <div>
    <!-- local storage 로컬 스토리지 웹사이트용 메모장 -->
    <div class="box">
      <h2>짐 보관 예약</h2>
      <input v-model="name" type="text" placeholder="이름을 입력해주세요." />
      <button @click="saveName">💾저장하기</button>
      <button @click="loadName">📰불러오기</button>
      <button @click="clearName">🗑삭제</button>
      <p>저장된 이름 : {{ savedName }}</p>
    </div>
  </div>
</template>
<script setup>
import { onMounted, ref } from "vue";

const name = ref("");
// 저장된 이름 보여주기
const savedName = ref("");
// 저장하기
const saveName = () => {
  localStorage.setItem("customerName", name.value);
  savedName.value = name.value; //저장 후 화면에 띄우기
  alert("이름이 저장되었습니다.");
};
// 불러오기
const loadName = () => {
  const getName = localStorage.getItem("customerName");
  console.log(getName);
  savedName.value = getName ? getName : "저장된 이름이 없어요";
};

// 지우기
const clearName = () => {
  localStorage.removeItem("customerName");
  savedName.value = "";
  alert("저장된 이름이 지워졌습니다.");
};

// 페이지 열릴 때 자동으로 불러오기
onMounted(() => {
  const getName = localStorage.getItem("customerName");
  if (getName) {
    saveName.value = getName;
  } else {
savedName.value = "저장된 이름이 없어요."  
}
// loadName()
});
</script>
<style scoped lang="scss"></style>

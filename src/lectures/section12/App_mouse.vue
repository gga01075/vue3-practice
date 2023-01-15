<template>
  <div>
    <div id="modifier">
      <div @click="clickDiv">
        DIV 영역
        <p @click="clickP">
          P 영역
          <span @click.stop="clickSpan">SPAN 영역</span>
        </p>
      </div>
      <a href="http://naver.com" @click.prevent="clickA">a영역</a>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const clickDiv = () => {
      console.log('clickDiv');
      location.href = 'http://naver.com';
    };
    const clickP = () => {
      console.log('clickP');
    };
    const clickSpan = e => {
      console.log('clickSpan');
      alert('좋아요');
    };

    const clickA = e => {
      console.log('clickA');
    };

    return { clickDiv, clickP, clickSpan, clickA };
  },
};
</script>

<style scoped>
#modifier div,
#modifier p,
#modifier span {
  padding: 40px;
}
#modifier div {
  background-color: #ccc;
}
#modifier p {
  background-color: #999;
}
#modifier span {
  background-color: #666;
  display: block;
}
</style>

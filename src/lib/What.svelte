<script>
  import Button from "$lib/Button.svelte";
  import Contact from "./X.svelte";
</script>

<div class="container grid">
  <div class="what">
    <h3>소개</h3>
    <p>   
      SSR은 한세사이버보안고등학교 정규동아리로 서울시 최초 IT 특성화 고등학교로 지정된 2001년 부터 학교와 함께해 왔습니다. 
      보안에 관심 있는 학생들끼리 모여 동아리를 만들고, 해킹이라는 흔치 않은 분야에서 서로가 서로를 도우며 보안을 공부해왔습니다. 
      체계적인 커리큘럼과 동아리원들의 열정,책임감은 22년이라는 역사를 뒷받침해왔습니다.
    </p>
  </div>


  <div class="logo">
   <div>
    <h3>ㅁㄴㅇㄹ</h3>
    <p>
      asdafsfsfsffsffdfasfsaffsf
    </p>
   </div>
  </div>
</div>

<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(13, 1fr);
    gap: 12em;
  }
  .what {
    grid-column: span 5;
  }
  .logo {
    grid-column: span 5;
  }

  h3 {
    padding-bottom: 0.5em;
    margin-bottom: 0.5em;
    font-size: 2em;
    font-weight: 500;
    border-bottom: 1px solid #ddd;
  }

</style>

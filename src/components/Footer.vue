<template>
    <div>
        <p class="footerp">{{info.editorName}}</p>
        <p class="footerp">{{info.date}}/{{info.month}}/{{info.year}}</p>
    </div>
</template>
<script>
export default {
    // props: ['editorName', 'date', 'month', 'year'],
    data: function(){
         var d = new Date();
      return {
          info : {
              editorName: "Jinjuta Limwattana",
               date: d.getDate(),
               month: d.getMonth(),
               year: d.getFullYear()
          }
      }
    }
}
</script>

<style>
.footerp {
    text-align: center;
    line-height: 0.5;
}
</style>
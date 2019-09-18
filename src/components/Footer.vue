<template>
    <div class="d-flex align-items-center">
        <p>{{info.editorName}}</p><br>
        <!-- <p>{{info.date}}</p> -->
    </div>
</template>
<script>
export default {
    // props: ['editorName', 'date', 'month', 'year'],
    data: function(){
        // var d = new date();
      return {
          info : {
              editorName: "Jinjuta Limwattana",
            //   date: d.getDate(),
          }
      }
    }
}
</script>>
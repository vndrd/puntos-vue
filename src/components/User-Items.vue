<template>
    <div class="col-md-10 user-item">
        <div class="immg">
          <img :src="require(`@/assets/${user.img}`)" class="rounded-circle"/>
        </div>
        <div class="prof">
          <h5>Usuario: <span>{{user.name}}</span></h5>
          <p>Puntos: <span>{{user.points}}</span></p>
          <a href="#" @click="btnDetalles">Detalles</a>
          <div class="listaDetalles" v-if="detBoolean" >
            <p v-for="(det,i) in detalles" :key="i">
              {{det.date}} | {{det.puntos}}
            </p>
          </div>
        </div>
    </div>
</template>
<script>

export default {
  name: 'User-Items',
  data() {
    return {
      detalles: [],
      clicked: false,
      detBoolean: false,
      nrandom: 0
    }
  },
  props: ['user'],
  created() {
      console.log("mounted ...........");
  },
  computed: { 
    image_url: function() {
       return this.imagePreUrl + this.$props.img;
    },
    getImgUrl() {
      var pet = this.$props.img;
      var images = require.context('@/assets/', false, /\.svg$/)
      return images('./' + pet + ".svg")
    }
  },
  methods:{
    btnDetalles: function(e){
      e.preventDefault();
      this.detBoolean = !this.detBoolean;
      if(!this.clicked){
        this.nrandom = parseInt(Math.random()*10+1);
        for (let i = 0; i < this.nrandom; i++) {
          let o = {puntos: 80};
          let date = this.randomDate(new Date(2020, 0, 1), new Date())
          o.date = date;
          this.detalles.push(o);
        }
        //console.log("todos los objetos: ",this.detalles)
      }
      this.clicked = true;
    },
    randomDate(start, end) {
      return new Date(start.getTime() + Math.random() * (end.getTime() - start.getTime()));
    }
  }

  // components: {
  //   HelloWorld
  // }
}
</script>

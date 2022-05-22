.<template>
  <div class="m-auto">


  <h1 class="text-2xl text-center">Dc heroes {{ heroesCount }}</h1>
  
  <ul>
    <li class="flex justify-between m-5" v-for="hero, index in dcHeroes" :key="hero.name">
      <div>{{hero.name}} 
      </div>
      <button @click="remove(index)">x</button>

    </li>
  </ul>
  <form class="mt-10" @submit.prevent="addHero">
    <input class="border rounded" v-model="newHero" placeholder="Type hero name here" />
    <button class="border rounded bg-gradient-to-r from-red-700 to green-500 text-sm text-white" type="submit">Add Hero</button>
  </form>
  </div>
</template>

<script>
export default {
    data(){
        return{
            newHero: "",
      dcHeroes: [
        { name: "SuperGirl" },
        { name: "Flash" },
        { name: "Arrow" },
        { name: "Batman" },
        { name: "SuperMan" },
      ],
        }
    },
    computed: {
    heroesCount() {
      return this.dcHeroes.length + " heroes";
    },
  },
  
  methods: {
    addHero() {
      if (this.newHero !== "") {
        this.dcHeroes.unshift({ name: this.newHero });
        this.newHero = "";
      }
    },
    remove(index) {
      this.dcHeroes = this.dcHeroes.filter((hero, i) => i !== index);
    },
  },
}

</script>

<style>

</style>
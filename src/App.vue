<template>
  <main>
    <h1>Javascript Quiz</h1>
    <div v-for="(question,index) in List" :key="index">
    <the-quiz v-if="index === i">
      
      <template #header>
        {{question.title}}
      </template>
      <template #main>
        <label v-for="(response,i) in question.responses" :key="i" :for="index">
              <input type="radio" :name="index" :value="response" v-model="res" />
           {{response}}
           </label>
      </template>
      <template #footer >
        <button @click="next" :disabled="!res">Next</button>
      </template>
   
    </the-quiz>
    
   </div>
   <div class="score" v-if="this.i == this.List.length">Score : {{ n.length }}</div>
  </main>
</template>

<script>
import TheQuiz from './components/TheQuiz.vue'
export default {
components: {
  TheQuiz
},
data() {
  return {
    List : [
  {
    title: "Why We Use <br> Element",
    responses: {
    answer_1: "To Make Text Bold",
    answer_2: "To Make Text Italic",
    answer_3: "To Add Breakline",
    answer_4: "To Create Horizontal Line",
    },
    right_answer: "To Add Breakline"
    

  },
  {
    title: "Is <img> Element Has Attribute href",
    responses: {
    answer_1: "Yes",
    answer_2: "No Its For Anchor Tag <a>",
    answer_3: "All Elements Has This Attribute",
    answer_4: "Answer 1 And 3 Is Right",
    },
    right_answer: "No Its For Anchor Tag <a>"
    
  },
  {
    title: "How Can We Make Element Text Bold",
    responses: {
    answer_1: "Putting It Inside <b> Tag",
    answer_2: "Putting It Inside <strong> Tag",
    answer_3: "Customizing It With Font-Weight Property In CSS",
    answer_4: "All Answers Is Right",
    },
    right_answer: "All Answers Is Right"
    
  },
  {
    title: "What Is The Right Hierarchy For Creating Part Of Page",
    responses: {
    answer_1: "<h2> Then <p> Then <h1> Then <p> Then <h3> Then <p> Then <img>",
    answer_2: "<h1> Then <p> Then <h3> Then <p> Then <h2> Then <p> Then <img>",
    answer_3: "<h2> Then <p> Then <h3> Then <p> Then <h1> Then <p> Then <img>",
    answer_4: "All Solutions Is Wrong"
    },
    
    right_answer: "All Solutions Is Wrong"
    
  },
  {
    title: "How Can We Include External Page Inside Our HTML Page",
    responses: {
    answer_1: "By Using Include in HTML",
    answer_2: "By Using Load In HTML",
    answer_3: "By Using iFrame Tag",
    answer_4: "All Solutions Is Wrong",
    },
    right_answer: "By Using iFrame Tag"
    
  },
  {
    title: "What Is The Tag That Not Exists in HTML",
    responses: {
    answer_1: "<object>",
    answer_2: "<basefont>",
    answer_3: "<abbr>",
    answer_4: "All Tags Is Exists in HTML",
    },
    right_answer: "All Tags Is Exists in HTML"
    
  },
  {
    title: "How We Specify Document Type Of HTML5 Page",
    responses: {
    answer_1: "<DOCTYPE html>",
    answer_2: "<DOCTYPE html5>",
    answer_3: "<!DOCTYPE html5>",
    answer_4: "<!DOCTYPE html>",
    },
    right_answer: "<!DOCTYPE html>"
    
  },
  {
    title: "What Is The Element Thats Not Exists in HTML5 Semantics",
    responses: {
    answer_1: "<article>",
    answer_2: "<section>",
    answer_3: "<blockquote>",
    answer_4: "<aside>",
    },
    right_answer: "<blockquote>"
  },
  {
    title: "In HTML Can We Use This Way To Add Attributes",
    responses: {
    answer_1: "<div class='class-name'>",
    answer_2: "<div class=class-name>",
    answer_3: "<div class=\"class-name\">",
    answer_4: "All Is Right",
    },
    right_answer: "All Is Right"
  }
],
i : 0,
res:null,
n:[],
selected:false
  }
},

  methods: {
    next () {
      if(this.res == this.List[this.i].right_answer){
      this.n.push(this.res)
      }
      this.res = null;
      this.i++;
      
    },
    check () {
      this.selected = true;
    }
  }
}



</script>

<style scoped>
main {
  background: #161b22;
  height: 100vh;
  display: flex;
  align-items: center;
  flex-direction: column;
}
h1 {
  margin-top: 50px;
  color: white;
  
}
label{
  display: block;
  padding: 20px;
}
button {
  background: #171a1d;
  color: white;
  padding: 10px 20px;
  transition: 0.3s ease-in;
  border-radius: 20px;
  font-weight: 500;
}
button:hover{
  color :#171a1d;
  background: white;
  
}
.score {
    background: #30363d;
    color: #f0f6fc;
    box-shadow: 1px 1px 5px 0 #f0f6fc;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 300px;
    font-size:62px;
    height:50%
}
</style>
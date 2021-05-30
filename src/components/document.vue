<template>

<div>
  <table class="table">
    <tr>
      <td>«Согласовано»<br>
        с Управляющим советом<br>
        от____20____г<br>
        Председатель УС:<br>
        {{name}}<br>
        подпись<br>
      </td>
      <td>«Утверждено» приказом<br>  
        от____20____г №_______ <br>
        Должность:<input class="inpt" v-model='post'> <br>
      </td>
    </tr>
  </table> 
</div>

<h1 class="title">ПОЛОЖЕНИЕ<br>
о разработке и реализации<br>
специальной индивидуальной программы развития обучающегося</h1>

<div>
  <h2>I. Цель и основание разработки и реализации СИПР</h2>
  <div  
  class="text"
  v-for="item in text1" 
  :key="item.id">
    <span class="id">{{item.id}}</span>
    {{item.text}}
    <div 
    class="text"
    v-if="item.id===1.2">
        <text>В соответствии с требованиями ФГОС образования обучающихся с
  интеллектуальными нарушениями и с учетом 2 варианта примерной АООП
  образования обучающихся с интеллектуальными нарушениями
  образовательная организация разрабатывает специальную индивидуальную
  программу развития (далее СИПР) под руководством {{name}}  в должности
  {{currentPost}}.
        </text>
    </div>
  </div>
</div>

<h2>II. Организация разработки СИПР</h2>
<div     
 class="text"
v-for="item in text2" 
:key="item.id">
  <div>
    <span class="id">{{item.id}}</span>
    {{item.text}}
  </div>
    
  <div v-if="item.id===2.3">
    <div 
    class="text"
    v-for="item in checkbox" 
    :key="item.id">
      <div class="item">
        <label >
          <input 
          type="checkbox" 
          v-model="checkboxValue" 
          :value='item.text' 
          name="checkboxValue">
          <span>{{item.text}}</span>
        </label>
      </div>
    </div>
  </div>

  <div v-if="item.id===2.4">
    <div>
      <div 
      class="text"
      v-for="item in radio" 
      :key="item.id">
        <div class="item">
          <label>
            <input type="radio" 
            v-model="radioValue" 
            :value="item.text" 
            name="radioValue">
            <span>{{item.text}}</span>
          </label>
        </div>
      </div>
    </div>
  </div>
</div>

<h2>III. Организация реализации СИПР</h2>
<div class="text"
v-for="item in text3" 
:key="item.id">
    <span class="id">{{item.id}}</span>
    {{item.text}}
</div>

</template>

<script>
export default {
    props:{
        name:{
            type:String
        }
    },
    data(){
        return{
            text1:[
                {id:1.1, text:"Широкий диапазон особых образовательных потребностей детей с умеренной, тяжелой, глубокой умственной отсталостью, с ТМНР вызываетнеобходимость образования таких обучающихся по индивидуальной программе. "},
                {id:1.2}
            ],
            text2:[
                {id:2.1, text:"При поступлении ребенка в образовательную организацию специалистыпроводят психолого-педагогическое обследование с целью последующейразработки СИПР и создания оптимальных условий ее реализации."},
                {id:2.2, text:"На основе результатов психолого-педагогического обследования ребенка,проводимого специалистами образовательной организации, составляетсяояния развития и определяется зона ближайшегоразвития обучающегося."},
                {id:2.3, text:"Структура характеристики включает:" },
                {id:2.4, text:"Программа сотрудничества специалистов с семьей обучающегося включаетперечень направлений сотрудничества, мероприятий и формсотрудничества организации и семьи обучающегося, а также частоту исроки проведения мероприятий.Программа сотрудничества специалистов с семьей обучающегосяпредусматривает:"}
            ],
            text3:[
                {id:2.5, text:'Реализация СИПР осуществляется группой, в которую входят те жеспециалисты, которые разрабатывали индивидуальную программу развития,и родителями (законными представителями) обучающегося.'},
                {id:2.6, text:'К анализу результатов обучения привлекаются члены семьи обучающегося.В ходе аттестации дается согласованная оценка достижений ребёнка в сфережизненных компетенций.'}
            ],
            checkbox:[
                {id:1,text:'чения в образовательной организации;'},
                {id:2,text:'сведения о семье (социально-бытовые условия, взаимоотношения в семье,отношение к ребенку)'},
                {id:3,text:'данные о физическом здоровье, двигательном и сенсорном развитииребенка;'},
                {id:4,text:'представления об окружающем мире (о себе, ближайшем окружении,природном, растительном, социальном мире)'},
                {id:5,text:'выводы по итогам оценки.'}
            ],
            radio:[
                {id:1,text:'психологическую поддержку семьи, консультации по всем вопросамоказания психолого-педагогической помощи ребенку;'},
                {id:2,text:'просвещение по вопросам воспитания и обучения ребенка-инвалида;'},
                {id:3,text:'регулярные контакты родителей и специалистов в течение всегоучебного года и др.'}
            ],
            radioValue:'',
            checkboxValue:[],
            post:'',
        }
    },
    methods:{
        log(){
            console.log(this.checkboxValue);
            console.log(this.radioValue);
            console.log(this.post);
        }
    },
    computed:{
        currentPost:function () {
            return this.post.toLowerCase()
        }
    }
}

</script>
<style  scoped>

table{
   border-collapse: collapse;
   margin-left: 850px;
   width: 450px;
   align-items: left;
   font-weight: 600;
}
td{
    border: 2px solid black
}
.id{
    position: relative;
    right: 70px;
}
.title{
    text-align: center;
    margin: auto;
    max-width: 770px;
    font-weight:800;
    margin-top: 70px;
    font-size: 20px;
}
.text{
    max-width: 720px;
    text-align: center;
    margin: auto;
    margin-top: 15px;
    font-size: 20px;
    text-align: justify;
}
.item{
   margin: 30px 30px;
   margin-top: 10px;
}
.inpt{
    width: 100px;
}



</style>
<template>
  <div class="hello">
    <div id='surveyElement'>
      <survey :survey="surveyModel"/>
    </div>
  </div>
</template>

<script>
import * as SurveyVue from 'survey-vue'
import surveyJSON from '@/assets/survey.json'

let Survey = SurveyVue.Survey

export default {
  name: 'HelloWorld',
  components: {
    Survey
  },
  computed: {
    surveyModel () {
      let survyeModel = new SurveyVue.Model(surveyJSON)
      survyeModel.onComplete.add(function (result) {
        alert(`result: ${JSON.stringify(result.data)}`)
      })
      return survyeModel
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

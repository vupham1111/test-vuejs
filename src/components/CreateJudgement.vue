<script>
import ItemContainer from "@/components/ItemContainer.vue";
import TargetContainer from "@/components/TargetContainer.vue";

export default {
  name: "CreateJudgement",
  components: {TargetContainer, ItemContainer},

  methods: {
    handleTriggerAddNew() {
      this.targetList.push({...this.defaultTarget})
    },
    handleSubmit() {
      // TODO call api here
      console.log(this.techZenGoalList)
      console.log(this.departmentGoalList)
      console.log(this.targetList)
    }
  },

  data() {
    return {

      techZenGoalList: {
        validationRuleList: [
          {
            behavior: "on-submit",
            condition: (value) => value.length === 0,
            error: "at least one"
          }
        ],
        error: "",
        value: [
          {
            validationRuleList: [
              {
                behavior: "on-submit",
                condition: (value) => value.length === 0,
                error: "at least one"
              }
            ],
            error: "",
            value: "xxx1"
          },
          {
            error: "",
            value: "xxx2"
          }
        ]
      },
      // techZenGoalList: [
      //   {name: "muc tieu 1"},
      //   {name: "muc tieu 2"},
      //   {name: "muc tieu 3"},
      // ],
      //
      // departmentGoalList: [
      //   {name: "muc tieu 1"},
      //   {name: "muc tieu 2"},
      //   {name: "muc tieu 3"},
      // ],

      defaultTarget: {
        targetName: {
          error: "",
          value: ""
        },
        stepList: {
          error: "",
          value: [
            {

            }
          ]
        }
      },

      targetList: {
        validationRule: [],
        error: "",
        value: [
        ]
      }

    }
  }
}
</script>

<template>
  <section class="grid grid-cols-[400px_1fr] gap-3">

    <article>
      <ItemContainer :data="techZenGoalList" title="Muc Tieu TechZen"/>
<!--      <ItemContainer :itemList="departmentGoalList" title="Muc Tieu Bo Phan"/>-->
    </article>

    <div>
<!--      <TargetContainer :targetList="targetList" />-->

      <div class="flex gap-2">
        <button @click="handleTriggerAddNew" class="bg-green-500">Add New Muc Tieu</button>
        <button @click="handleSubmit" class="bg-blue-500">Submit</button>
        <button class="bg-red-500">Huy</button>
      </div>
    </div>

    <div class="flex flex-col gap-4">
<!--      <div>-->
<!--        <strong>target list</strong>-->
<!--        <p>{{targetList}}</p>-->
<!--        <p>//////////////</p>-->
<!--      </div>-->

      <div>
        <strong>techZenGoalList</strong>
        <p>{{techZenGoalList}}</p>
        <p>//////////////</p>
      </div>

<!--      <div>-->
<!--        <strong>departmentGoalList</strong>-->
<!--        <p>{{departmentGoalList}}</p>-->
<!--        <p>//////////////</p>-->
<!--      </div>-->
    </div>

  </section>
</template>

<style scoped>

</style>
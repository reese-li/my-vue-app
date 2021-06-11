<template>
  <div>

 
    <b-form-group
      label="Table Variant"
      label-for="table-style-variant"
      label-cols-lg="2"
    >
      <b-form-select
        v-model="selected"
        :options="items"
        value-field="id"
        text-field="first_name"
        id="table-style-variant"
        v-on:change="getSelectedItem"
      >
        <template v-slot:first>
          <option value="all">-- All --</option>
        </template>
      </b-form-select>
    </b-form-group>
  <div>{{selected}}</div>
  

    <b-table
      :striped="striped"
      :bordered="bordered"
      :borderless="borderless"
      :outlined="outlined"
      :small="small"
      :hover="hover"
      :dark="dark"
      :fixed="fixed"
      :foot-clone="footClone"
      :no-border-collapse="noCollapse"
      :items="tableData"
      :fields="fields"
    ></b-table>
  </div>
</template>

<script>

export default {
  data() {
    return {
      fields: [{ first_name: "名字" }, { last_name: "姓氏" }, { age: "年龄" }],
      items: [
        { age: 40, first_name: "Dickerson", last_name: "Macdonald", id:'0'   },
        { age: 21, first_name: "Larsen", last_name: "Shaw" , id: '1'},
        { age: 89, first_name: "Geneva", last_name: "Wilson", id:'2' },
      ],
      selected:0,
      tableData: []
    }; 
  },
    mounted(){
       this.tableData=this.items
    },
    methods:{
        getSelectedItem(){
            if(this.selected=='all'){
                this.tableData = this.items;
            }else{
                this.tableData=[this.items[this.selected]]
            }
            console.log(this.tableData)
        }

    }
};

</script>


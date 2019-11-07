<template>
  <div>
    <myheader></myheader>
    <form @submit.prevent="completeItem">
      <p>国籍</p>
      <div>
        <input type="text" v-model="country" />
      </div>
      <p>性別:</p>
      <div>
        <select v-model="selected">
          <option></option>
          <option>男性</option>
          <option>女性</option>
          <option>その他</option>
          <option>回答しない</option>
        </select>
      </div>

      <p>生年月日:</p>
      <div>
        <input type="date" v-model="dated" />
      </div>

      <p>住所:</p>
      <div>
        <input type="text" value="〒" />
      </div>
      <div>
        <textarea
          v-on:mouseover="mouseover"
          v-on:mouseleave="mouseleave"
          v-model="address"
          rows="4"
          cols="40"
        ></textarea>
      </div>

      <p>職業:</p>
      <div>
        <input type="text" v-model="work" />
      </div>
      <p>電話番号:</p>
      <div>
        <input type="tel" v-model="tell" />
      </div>

      <p>宿泊人数:</p>
      <div>
        <select name="人数" v-model="people">
          <option></option>
          <option>1</option>
          <option>2</option>
          <option>3</option>
          <option>4</option>
          <option>5</option>
          <option>6</option>
          <option>7</option>
          <option>8</option>
        </select>
      </div>
      <p>署名</p>
      <div>
        <textarea v-model="name"></textarea>
      </div>

      <input type="submit" value="complete" />
    </form>
  </div>
</template>

<script>
import myheader from "./components/myheader";

export default {
  components: {
    myheader
  },
  data() {
    return {
      country: "",
      selected: "",
      dated: "",
      address: "都道府県から記述してください",
      work: "",
      tell: "",
      people: "",
      name: ""
    };
  },
  methods: {
    mouseover() {
      this.address = "";
    },
    mouseleave() {
      this.address = "Hover Me!";
    },
    completeItem() {
      console.log(this.country);
      console.log(this.selected);
      console.log(this.dated);
      console.log(this.address);
      console.log(this.work);
      console.log(this.tell);
      console.log(this.people);
      console.log(this.name);
    }
  }
};
</script>
<template>
  <div>{{fullName}}</div>
  <button @click="changename">click</button>
</template>

<script>
export default {
  name: 'ComPutedGetSet',
  data () {
    return {
      firstName: 'ac',
      lastName: 'b'
    };
  },

  computed: {
    // fullName: function() {
    //   return this.firstName + ' ' + this.lastName
    // }
    fullName: {
      set(newVal) {
        let newName = newVal.split(' ');
        this.firstName = newName[0];
        this.lastName = newName[1];
      },
      get() {
        return this.firstName + ' ' + this.lastName;
      }
    }
  },

  methods: {
    changename() {
      this.fullName = 'acd bcd';
    }
  }
}

</script>
<style lang='less' scoped>
</style>

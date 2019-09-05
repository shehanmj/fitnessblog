<template>
  <div >
    <b-form class="container" @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1">
        <b-form-input
          id="input-1"
          v-model="form.title"
          type="text"
          required
          placeholder="Enter Title"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2">
        <b-form-textarea
          id="input-2"
          v-model="form.body"
          required
          placeholder="Your words go here!"
        ></b-form-textarea>
      </b-form-group>
<b-form-group id="input-group-3">
        <b-form-file
         v-model="form.file"
         :state="Boolean(form.file)"
         placeholder="Choose a photo or drop it here..."
         drop-placeholder="Drop file here..."
        ></b-form-file>
</b-form-group>
      <b-button class="buttons" type="submit" variant="primary">Submit</b-button>
      <b-button class="buttons" type="reset" variant="danger">Reset</b-button>
    </b-form>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          title: '',
          body: '',
          file: {},
        },
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.title = ''
        this.form.body = ''
        this.form.file = {}
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>

<style scoped>
.container {
    margin: auto;
    width: 600px;
}
.buttons {
    margin: 10px;
}

#input-2 {
    height: 500px;
    overflow-y: scroll;
    vertical-align: text-top;
}
</style>
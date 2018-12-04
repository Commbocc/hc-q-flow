<template>
  <div id="app">

    <p class="lead">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

    <div class="card mb-3">
      <div class="card-header bg-primary text-white lead">
        <span class="fas fa-hand-paper fa-fw"></span>
        <strong class="font-weight-bold">
          Hillsborough County Customer Varification
        </strong>
      </div>
      <div class="card-body">
        <em>
          Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. Nihil anim keffiyeh helvetica, craft beer labore.
          <strong>Am I a Hillsborough County customer?</strong>
        </em>

        <div class="input-group my-3">
          <input type="text" class="form-control" placeholder="My Address" aria-label="My Address" aria-describedby="button-addon2">
          <div class="input-group-append">
            <button class="btn btn-outline-secondary" type="button" id="button-addon2">Search</button>
          </div>
        </div>

        <div class="form-check mt-2">
          <input v-model="varify" class="form-check-input" type="checkbox" value="" id="defaultCheck1">
          <label class="form-check-label" for="defaultCheck1">
            I am a customer of Hillsborough County
          </label>
        </div>

        <div class="row mt-3">
          <div class="col-md-6">
            <a class="btn btn-primary text-white btn-lg btn-block" :class="btnVarified">
              Get in Line
              <span class="fas fa-fw fa-ticket-alt"></span>
            </a>
          </div>
          <div class="col-md-6">
            <a href="#" class="btn btn-primary text-white btn-lg btn-block">
              My Tickets
              <span class="fas fa-fw fa-user-circle"></span>
            </a>
          </div>
        </div>

      </div>
    </div>

    <table is="IwtTable" class="my-3"></table>

    <h3>Lorem Ipsum</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>


  </div>
</template>

<script>
import IwtTable from './components/Iwt'
export default {
  components: { IwtTable },
  data () {
    return {
      varify: false,
      msg: 'Welcome to Your Vue.js App'
    }
  },
  computed: {
    btnVarified () {
      return (this.varify) ? null : 'disabled'
    }
  }
}
</script>

<style src="./assets/main.scss" lang="scss"></style>

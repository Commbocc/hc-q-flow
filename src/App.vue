<template>
  <div id="app">

    <p class="lead">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

    <!-- <pre class="p-3 bg-light">{{ $data }}</pre> -->

    <div class="card mb-3">
      <div class="card-header bg-primary text-white">
        <span class="fas fa-hand-paper fa-fw"></span>
        <strong class="font-weight-bold">
          Hillsborough County Customer Verification
        </strong>
      </div>
      <div class="card-body">
        <p>
          <em>
            Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. Nihil anim keffiyeh helvetica, craft beer labore.
            <strong>Am I a Hillsborough County customer?</strong>
          </em>
        </p>

        <form is="HcEsriSearchWidget" @submit="reset" @result="handleResult"></form>

        <form>
          <div class="form-check">
            <input v-model="verify" class="form-check-input" type="checkbox" value="" id="countyVerification">
            <label class="form-check-label" for="countyVerification">
              I am a customer of Hillsborough County
            </label>
          </div>
        </form>

        <div class="row mt-3">
          <div class="col-md-6">
            <a class="btn btn-primary text-white btn-lg btn-block mb-1" :class="btnVerified">
              Get in Line
              <span class="fas fa-fw fa-ticket-alt"></span>
            </a>
          </div>
          <div class="col-md-6">
            <a href="#" class="btn btn-primary text-white btn-lg btn-block mb-1">
              My Tickets
              <span class="fas fa-fw fa-user-circle"></span>
            </a>
          </div>
        </div>

      </div>
    </div>

    <table is="IwtTable" class="my-3"></table>

    <h3>Lorem Ipsum</h3>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </p>


  </div>
</template>

<script>
import HcEsriSearchWidget from 'hc-esri-search-widget'
import IwtTable from './components/Iwt'

export default {
  components: { IwtTable, HcEsriSearchWidget },
  data () {
    return {
      verify: false
    }
  },
  methods: {
    reset () {
      console.log('reset')
    },
    handleResult (searchResult) {
      let url = 'https://services.arcgis.com/apTfC6SUmnNfnxuF/ArcGIS/rest/services/County_Boundary/FeatureServer/0'
      searchResult.queryFeatures(url).then(features => {
        this.verify = (features) ? true : false
      }).catch(err => {
        this.verify = false
      })
    }
  },
  computed: {
    btnVerified () {
      return (this.verify) ? null : 'disabled'
    }
  }
}
</script>

<style src="./assets/main.scss" lang="scss"></style>

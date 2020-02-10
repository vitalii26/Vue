<<template>
  <div class="sites__create">
    <div class="container">
      <b-form class="bg-light pb-4 px-3 text-secondary">
        <div class="row mb-4">
          <div class="col-12 d-flex justify-content-between bg-white p-2">
            <h2>Add New Site</h2>
            <div class="button">
              <b-icon-question class="h2"></b-icon-question>
            <b-icon-camera-video class="h2"></b-icon-camera-video>
            </div>
          </div>
        </div>
        <b-form-group
          id="fieldset-horizontal"
          label-cols-sm="4"
          label-cols-lg="3"
          label="URL"
          label-for="input-horizontal"
        >
          <b-input-group size="lg" prepend="http(s)://">
            <b-form-input  placeholder="Your site"></b-form-input>
          </b-input-group>
        </b-form-group>
        <b-form-group
            id="fieldset-horizontal"
            label-cols-sm="4"
            label-cols-lg="3"
            label="Server"
            label-for="input-horizontal"
          >
          <b-form-select></b-form-select>
        </b-form-group>
        <b-form-group
            id="fieldset-horizontal"
            label-cols-sm="4"
            label-cols-lg="3"
            label="System user"
            label-for="input-horizontal"
          >
          <b-form-select></b-form-select>
        </b-form-group>
        <b-form-group
            id="fieldset-horizontal"
            label-cols-sm="4"
            label-cols-lg="3"
            label="Bundles"
            label-for="input-horizontal"
          >
          <b-form-select></b-form-select>
        </b-form-group>
        <b-form-group label="Advanced options"
          label-cols-sm="3"
          label-cols-lg="3">
          <b-form-checkbox-group
            id="checkbox-group-1"
            v-model="selected"
            :options="options"
            name="flavour-1"
            class="mb-4"
          ></b-form-checkbox-group>
        </b-form-group>
         <b-button variant="info"><b-icon-check-circle></b-icon-check-circle>Add Site</b-button>
      </b-form>
    </div>
  </div>
</template>

<script>
  import { BIconQuestion, BIconCameraVideo, BIconCheckCircle } from 'bootstrap-vue'
  export default {
    data() {
      return {
        selected: []
        
      }
    },
    props: ['options'],
    components: {
      BIconQuestion,
      BIconCameraVideo,
      BIconCheckCircle
    },
    methods: {
      }
    }
</script>
<style scoped>
  .button {
    position: relative;
    width: 100%;
    max-width: 70px;
    display: flex;
    justify-content: space-between;
  }
  .button ::after {
    display: block;
    content: '';
    width: 1px;
    height: 1rem;
    background-color: black;
    position: absolute;
    top: 0;

  }
  .sites__create {
    margin-bottom: 40px;
  }
</style>
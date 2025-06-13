<template>
  <div>
    <h2>Dark Theme Demo</h2>
    <p>This demo shows the <code>vue-dropzone</code> component with the <code>theme="dark"</code> prop.</p>
    <vue-dropzone
      id="dropzone-dark"
      ref="dropzoneDark"
      :options="dropzoneOptions"
      :theme="'dark'"
      @vdropzone-success="handleSuccess"
      style="min-height: 200px; width: 100%;"
    >
    </vue-dropzone>
    <hr />
    <h3>Configuration:</h3>
    <pre><code class="language-javascript">
export default {
  components: {
    vueDropzone: vue2Dropzone
  },
  data() {
    return {
      dropzoneOptions: {
        url: "https://httpbin.org/post", // Replace with your actual upload URL
        thumbnailWidth: 150,
        maxFilesize: 2, // MB
        addRemoveLinks: true,
        dictDefaultMessage: "<i class='fa fa-cloud-upload'></i> Drop files here or click to upload (Dark Theme)"
      }
    };
  },
  methods: {
    handleSuccess(file, response) {
      console.log("File uploaded successfully:", file, response);
    }
  }
};
    </code></pre>
  </div>
</template>

<script>
import vue2Dropzone from "../../../src/components/vue-dropzone.vue"; // Adjust path as necessary

export default {
  name: "DarkThemeDemo",
  components: {
    vueDropzone: vue2Dropzone
  },
  data() {
    return {
      dropzoneOptions: {
        url: "https://httpbin.org/post", // Using a public endpoint for demo
        thumbnailWidth: 150,
        maxFilesize: 2, // MB
        addRemoveLinks: true,
        dictDefaultMessage:
          "<i class='fa fa-cloud-upload'></i> Drop files here or click to upload (Dark Theme)"
      }
    };
  },
  methods: {
    handleSuccess(file, response) {
      console.log("Dark Theme Demo: File uploaded successfully:", file, response);
      // You can add further handling here, like displaying a success message
    }
  }
};
</script>

<style scoped>
/* Add any specific styles for this demo page if needed */
h2 {
  margin-bottom: 20px;
}
p {
  margin-bottom: 15px;
}
hr {
  margin-top: 30px;
  margin-bottom: 30px;
}
pre {
  background-color: #f5f5f5;
  padding: 15px;
  border-radius: 4px;
  overflow-x: auto;
}
code.language-javascript {
  color: #333;
}
</style>

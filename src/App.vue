 <template>
  <div>
    <h1>Feedback Form</h1>
    <p>We would love to heat your thoughts, suggestions, concerns</p>
  </div><br>
  <div>
    <h3>Feedback Type</h3>
    <div>Picked: {{ picked }}</div>
    <input type="radio" id="Comments" value="Comments" v-model="picked">
    <label for="Comments">Comments</label>
    <input type="radio" id="Suggestions" value="Suggestions" v-model="picked">
    <label for="Suggestions">Suggestions</label>
    <input type="radio" id="Questions" value="Questions" v-model="picked">
    <label for="Questions">Questions</label><br>  
    <span>Describe Your Feedback</span>
    <p>{{ message }}</p>
    <textarea v-model="message" placeholder="add multiple lines"></textarea><br><br>
    <h3>Name*</h3>
    <input type="text">
    <input type="text"><br><br>
    <h3>Email</h3>
    <input type="text" placeholder="ex: murodov@gmail.com">
    <p>ex: murodov@gmail.com</p>
  </div><br><br>

  <div class="submet">
    <button>SUBMIT</button>
  </div>
</template>

<script>
export default {
  props: ["modelValue"],
  emits: ["update:modelValue"],
  data() {
    return {
      cart: [
        { id: 1, name: "Product A", price: 50 },
        { id: 2, name: "Product B", price: 30 },
        { id: 3, name: "Product C", price: 20 },
      ],
      picked:'three'
    };
  },
  computed: {
    totalPrice() {
      return this.cart.reduce((total, item) => total + item.price, 0);
    },
  },
  methods: {
    totalPriceFn(num) {
      return this.cart.reduce((total, item) => total + item.price, num);
    },
    submitFn() {
      console.log("dasfdf");
    },
  },
};
</script>

<template>
  <div id="sorting" class="section">
    <div class="title">
      SORTING
    </div>
    <div id="random">
      <div class="sorting-options">
        <span class="option">
          <label for="arraySize">Size :</label>
          <select id="arraySize" v-model.number="arraySize">
            <option>50</option>
            <option>40</option>
            <option>30</option>
            <option>20</option>
            <option>10</option>
          </select>
        </span>
        <span class="option">
          <label for="timerInterval">Timer interval (in millisec) :</label>
          <select id="timerInterval" v-model.number="timerInterval">
            <option>100</option>
            <option>500</option>
            <option>1000</option>
          </select>
        </span>
        <button v-on:click="setRandomArray()">Generate Random Array</button>
        <button v-on:click="sortArray()">Sort</button>
      </div>
      <div v-if="array.length > 0">
        <graph-bar
            :width="array.length * 30"
            :height="400"
            :axis-min="0"
            :axis-max="array.length"
            :labels="labels"
            :values="array">
          <note :text="'Random array'"></note>
        </graph-bar>
      </div>
      <!--<b-container class="bv-example-row">
          <b-row>
              <b-col>1 of 3</b-col>
              <b-col>2 of 3</b-col>
              <b-col>3 of 3</b-col>
          </b-row>
      </b-container>
      -->
      <b-container>
          <b-row>
              <b-col>
                <div v-if="bubbleArray.length > 0">
                  <graph-bar
                      :width="bubbleArray.length * 30"
                      :height="400"
                      :axis-min="0"
                      :axis-max="bubbleArray.length"
                      :labels="labels"
                      :values="bubbleArray">
                    <note :text="'Bubble Sorted array'"></note>
                  </graph-bar>
                </div>
              </b-col>
              <b-col>
                <div v-if="insertionArray.length > 0">
                  <graph-bar
                      :width="insertionArray.length * 30"
                      :height="400"
                      :axis-min="0"
                      :axis-max="insertionArray.length"
                      :labels="labels"
                      :values="insertionArray">
                    <note :text="'Insertion Sorted array'"></note>
                  </graph-bar>
                </div>
              </b-col>
          </b-row>
          <b-row>
            <b-col>
              <div v-if="selectionArray.length > 0">
                <graph-bar
                    :width="selectionArray.length * 30"
                    :height="400"
                    :axis-min="0"
                    :axis-max="selectionArray.length"
                    :labels="labels"
                    :values="selectionArray">
                  <note :text="'Selection Sorted array'"></note>
                </graph-bar>
              </div>
            </b-col>
            <b-col>
              <div v-if="quickSortArray.length > 0">
                <graph-bar
                    :width="quickSortArray.length * 30"
                    :height="400"
                    :axis-min="0"
                    :axis-max="quickSortArray.length"
                    :labels="labels"
                    :values="quickSortArray">
                  <note :text="'QuickSort Sorted array'"></note>
                </graph-bar>
              </div>
            </b-col>
          </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Sorting',
  props: {
    msg: String
  },
  data() {
    return {
        array : [],
        arraySize : 40,
        timerInterval : 100,
        labels: [],
        bubbleArray : [],
        insertionArray : [],
        selectionArray : [],
        quickSortArray: [],
        quickSortArraySteps: [],
        stopSort: true,
        timerId: undefined
    }
  },
  methods: {
    setRandomArray() {
      this.stopSort = true;
      clearInterval(this.timerId);
      this.array = this.shuffle(this.arraySize);
      this.bubbleArray = this.array.slice();
      this.insertionArray = this.array.slice();
      this.selectionArray = this.array.slice();
      this.quickSortArray = this.array.slice();
      this.labels = this.init(this.arraySize);
    },
    init(size) {
      var array = [];
      for (var i=0;i<size;++i) {
          array[i]=i;
      }
      return array;
    },
    shuffle() {
      var array = this.init(this.arraySize);
      var tmp, current, top = array.length;
      if(top) {
        while(--top) {
          current = Math.floor(Math.random() * (top + 1));
          tmp = array[current];
          array[current] = array[top];
          array[top] = tmp;
        }
      }
      return array;
    },
    sortArray() {
      this.stopSort = true;
      clearInterval(this.timerId);
      if(this.array.length === 0){
        this.setRandomArray(this.arraySize);
      }
      var bubbleArraySteps = this.bubbleSort();
      var insertionArraySteps = this.insertionSort();
      var selectionArraySteps = this.selectionSort();
      this.quickSort();
      this.stopSort = false;
      this.startInterval(bubbleArraySteps, insertionArraySteps, selectionArraySteps, this.quickSortArraySteps);
    },
    startInterval(bubbleArraySteps, insertionArraySteps, selectionArraySteps, quickSortArraySteps) {
      var i = 0;
      var max = Math.max(bubbleArraySteps.length, insertionArraySteps.length, selectionArraySteps.length, quickSortArraySteps.length);
      this.timerId = setInterval(() => {
        if (i < bubbleArraySteps.length) {
          this.bubbleArray = bubbleArraySteps[i];
        }
        if (i < insertionArraySteps.length) {
          this.insertionArray = insertionArraySteps[i];
        }
        if (i < selectionArraySteps.length) {
          this.selectionArray = selectionArraySteps[i];
        }
        if (i < quickSortArraySteps.length) {
          this.quickSortArray = quickSortArraySteps[i];
        }
        i++;
        if (i === max || this.stopSort) {
          clearInterval(this.timerId);
        }
      }, this.timerInterval);
    },
    bubbleSort(){
      var sortedArray = this.array.slice();
      var bubbleArraySteps = [];
      var swapped;
      do {
        swapped = false;
        for (var i=0; i < sortedArray.length-1; i++) {
          if (sortedArray[i] > sortedArray[i+1]) {
            var temp = sortedArray[i];
            sortedArray[i] = sortedArray[i+1];
            sortedArray[i+1] = temp;
            swapped = true;
            bubbleArraySteps.push(sortedArray.slice());
          }
        }
      } while (swapped);
      return bubbleArraySteps;
    },
    insertionSort() {
      var sortedArray = this.array.slice();
      var insertionArraySteps = [];
      for (var i = 0; i < sortedArray.length; i++) {
        let value = sortedArray[i];
        var storeSteps = false;
        // store the current item value so it can be placed right
        for (var j = i - 1; j > -1 && sortedArray[j] > value; j--) {
          // loop through the items in the sorted array (the items from the current to the beginning)
          // copy each item to the next one
          storeSteps = true;
          sortedArray[j + 1] = sortedArray[j]
          insertionArraySteps.push(sortedArray.slice());
        }
        // the last item we've reached should now hold the value of the currently sorted item
        sortedArray[j + 1] = value
        if(storeSteps) {
          insertionArraySteps.push(sortedArray.slice());
        }
      }

      return insertionArraySteps;
    },
    selectionSort(){
      var sortedArray = this.array.slice();
      var selectionArraySteps = [];
      var minIdx, temp,
          len = sortedArray.length;
      for(var i = 0; i < len; i++){
        minIdx = i;
        for(var  j = i + 1; j < len; j++){
           if(sortedArray[j] < sortedArray[minIdx]){
              minIdx = j;
           }
        }
        temp = sortedArray[i];
        sortedArray[i] = sortedArray[minIdx];
        selectionArraySteps.push(sortedArray.slice());
        sortedArray[minIdx] = temp;
        selectionArraySteps.push(sortedArray.slice());
      }
      return selectionArraySteps;
    },
    quickSort(){
      var sortedArray = this.array.slice();
      this.quickSortArraySteps = [];
      this.quickSortAlgo(sortedArray, 0, sortedArray.length - 1);
    },
    quickSortAlgo(arr, left, right){
      var pivot,
      partitionIndex;

      if(left < right){
        pivot = right;
        partitionIndex = this.partition(arr, pivot, left, right);

        //sort left and right
        this.quickSortAlgo(arr, left, partitionIndex - 1);
        this.quickSortAlgo(arr, partitionIndex + 1, right);
      }
    },
    partition(arr, pivot, left, right){
      var pivotValue = arr[pivot],
          partitionIndex = left;

      for(var i = left; i < right; i++){
        if(arr[i] < pivotValue){
          this.swap(arr, i, partitionIndex);
          partitionIndex++;
        }
      }
      this.swap(arr, right, partitionIndex);
      return partitionIndex;
    },
    swap(arr, i, j){
       var temp = arr[i];
       arr[i] = arr[j];
       this.quickSortArraySteps.push(arr.slice());
       arr[j] = temp;
       this.quickSortArraySteps.push(arr.slice());
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section {
  float: right;
  height: 100vh;
  padding-top: 60px;
  width: 100%;
}
.title{
  float: left;
  padding: 0 0 0 250px;
  font-size: 30px;
  text-align: left;
  text-transform: uppercase;
}
.sorting-options{
  float: left;
  padding-top: 50px;
}
.option{
  padding-right: 10px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

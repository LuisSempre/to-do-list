<template>
  <div class="task"
        :class="stateClass">
      <p>{{ task.name }}</p>
  </div>
</template>

<script>
export default {
    props: {
        task: { type: Object, required: true}
    },
    computed: {
        stateClass() {
            return {
                pending: this.task.pending,
                done: !this.task.pending
            }
        }
    }
}
</script>

<style>
.task {
    box-sizing: border-box;
    width: 150px;
    height:  150px;
    padding: 10px;
    border-radius: 8px;
    font-size: 2rem;
    font-weight: 300;
    cursor: pointer;
    user-select: none;
    display: flex;
    justify-content: center;
    align-items: center;
}

.pending {
    border-left: 12px solid rgb(255, 136, 0);
    background-color: orange;
}

.done {
    color: rgba(255, 255, 255, 0.384);
    border-left: 12px solid rgb(0, 128, 64);
    background-color: green;
    text-decoration: line-through;
}
</style>
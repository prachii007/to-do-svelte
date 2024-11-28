<script>
  import { goto } from '$app/navigation'
  const priority = $state([])
  const priorityLabels = ['All', 'High', 'Medium', 'Low']
  const tagLabels = ['study', 'work', 'shopping']
  let action = $state('All')
  const handleAddTask = () => {
    goto('/add')
  }
  const handleDelete = () => {}
  const handleDeleteAll = () => {}
  const handleEdit = () => {}
</script>

<div>
  <div class="">
    <h1 class="text-center">Task List</h1>
    <div class="row">
      <div>
        <button class="btn btn-danger" onclick={handleAddTask}>Add Task</button>
        <div class="btn btn-group">
          <button class="btn btn-primary" onclick={(action = 'All')}>
            Show All
          </button>
          <button class="btn btn-warning" onclick={(action = 'Unchecked')}>
            Show Unchecked
          </button>
          <button class="btn btn-success" onclick={(action = 'Checked')}>
            Show Checked
          </button>
        </div>
        <div class="d-flex">
          <div for="sortOrder">Date of creation :</div>
          <div class="d-flex">
            <div class="mx-2 d-flex">
              <label for="latest">Latest</label>
              <input
                type="radio"
                name="sortOrder"
                value="desc"
                class="form-check ms-2"
                id="latest"
              />
            </div>
            <div class="d-flex">
              <label for="oldest">Oldest</label>
              <input
                type="radio"
                name="sortOrder"
                value="asc"
                class="form-check ms-2"
                id="oldest"
              />
            </div>
          </div>
        </div>
        <div class="d-flex mt-3">
          <div class="me-4">
            <div>Priority:</div>
            {#each priorityLabels as label (label)}
              <div class="d-flex align-items-center">
                <input type="checkbox" id={label} class="form-check" />
                <label class="ms-2" for={label}>{label}</label>
              </div>
            {/each}
          </div>
          <div>
            <div>Tags:</div>
            {#each tagLabels as label (label)}
              <div class="d-flex align-items-center">
                <input type="checkbox" id={label} class="form-check" />
                <label class="ms-2" for={label}>{label}</label>
              </div>
            {/each}
          </div>
        </div>
      </div>
    </div>
    <div>
      <div class="d-flex justify-content-center mt-4">
        <h2>{action} Tasks()</h2>
        <button class="btn btn-danger ms-2">Delete All</button>
      </div>
      <!-- <TaskCard
        v-for="todo in filteredTodos"
        :key="todo.id"
        :todo="todo"
        :handleCheck="handleCheck"
        :handleEdit="handleEdit"
        :handleDelete="handleDelete"
      /> -->
    </div>
  </div>
</div>

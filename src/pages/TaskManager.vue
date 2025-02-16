<template>
  <div class="content">
    <base-table :data="tableData" :columns="columns">
      <template slot="columns">
        <th class="text-center">#</th>
        <th>TaskName</th>
        <th>CreateTime</th>
        <th>Reading each time</th>
        <th>Completion Rate</th>
        <th>Actions</th>
      </template>
      <template slot-scope="{ row }">
        <td>{{ row.id }}</td>
        <td>{{ row.TaskName }}</td>
        <td>{{ row.CreateTime }}</td>
        <td>{{ row.read_per_time }}</td>
        <td>{{ row.Rate }}</td>
        <td class="td-actions">
          <base-button type="info" size="m" icon>Info </base-button>
          <base-button type="success" size="m" icon>
            <i class="tim-icons icon-button-pause"></i>
          </base-button>
          <base-button type="danger" size="m" icon>
            <i class="tim-icons icon-triangle-right-17"></i>
          </base-button>
          <base-button type="success" size="m" icon>
            <i class="tim-icons icon-refresh-01"></i>
          </base-button>
          <base-button type="info" size="m" icon>
            <i class="tim-icons icon-simple-add"></i>
          </base-button>
        </td>
      </template>
    </base-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      columns: [
        "id",
        "TaskName",
        "CreateTime",
        "read_per_time",
        "Rate",
        "actions",
      ],
      tableData: [
        {
          id: 1,
          TaskName: "Task A",
          CreateTime: "2023-01-01",
          read_per_time: "10%",
          Rate: "90%",
          actions: "Edit/Delete",
        },
        {
          id: 2,
          TaskName: "Task B",
          CreateTime: "2023-01-02",
          read_per_time: "20%",
          Rate: "85%",
          actions: "Edit/Delete",
        },
        {
          id: 3,
          TaskName: "Task C",
          CreateTime: "2023-01-03",
          read_per_time: "15%",
          Rate: "95%",
          actions: "Edit/Delete",
        },
      ],
    };
  },
};
</script>

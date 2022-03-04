<template>
  <div>
    <q-table
      title="Page Visits"
      :rows="rows"
      :columns="columns"
      color="primary"
      row-key="name"
    >
      <template v-slot:top-right>
        <q-btn
          color="primary"
          icon-right="archive"
          label="Export to csv"
          no-caps
          @click="exportTable"
        />
      </template>
    </q-table>
  </div>
</template>

<script>
import { exportFile, useQuasar } from 'quasar'

const columns = [
  {
    name: 'name',
    required: true,
    label: 'User ID',
    align: 'left',
    field: row => row.name,
    format: val => `${val}`,
    sortable: true
  },
  { name: 'User_Name', align: 'center', label: 'User Name', field: 'User_Name', sortable: true },
  { name: 'Page', label: 'Page', field: 'Page', sortable: true },
  { name: 'Date', label: 'Date', field: 'Date' }
]

const rows = [
  {
    name: 'U0001',
    User_Name: 'Shakeel Ahmad',
    Page: 'All Pages',
    Date:'28-02-2022'
  },
   {
    name: 'U0001',
    User_Name: 'Javed ch',
    Page: 'Login',
    Date:'12-10-2021'
  },
   {
    name: 'U0001',
    User_Name: 'Saeed Ansari',
    Page: 'Services',
    Date:'12-02-2022'
  },
   {
    name: 'U0001',
    User_Name: 'Akhlaq Ahmed',
    Page: 'Cards',
    Date:'12-10-2021'
  },
   {
    name: 'U0001',
    User_Name: 'Azlan',
    Page: 'Mail',
    Date:'28-02-2020'
  },
]

function wrapCsvValue (val, formatFn) {
  let formatted = formatFn !== void 0
    ? formatFn(val)
    : val

  formatted = formatted === void 0 || formatted === null
    ? ''
    : String(formatted)

  formatted = formatted.split('"').join('""')
  /**
   * Excel accepts \n and \r in strings, but some other CSV parsers do not
   * Uncomment the next two lines to escape new lines
   */
  // .split('\n').join('\\n')
  // .split('\r').join('\\r')

  return `"${formatted}"`
}

export default {
  setup () {
    const $q = useQuasar()

    return {
      columns,
      rows,

      exportTable () {
        // naive encoding to csv format
        const content = [columns.map(col => wrapCsvValue(col.label))].concat(
          rows.map(row => columns.map(col => wrapCsvValue(
            typeof col.field === 'function'
              ? col.field(row)
              : row[ col.field === void 0 ? col.name : col.field ],
            col.format
          )).join(','))
        ).join('\r\n')

        const status = exportFile(
          'table-export.csv',
          content,
          'text/csv'
        )

        if (status !== true) {
          $q.notify({
            message: 'Browser denied file download...',
            color: 'negative',
            icon: 'warning'
          })
        }
      }
    }
  }
}
</script>

<template>
  <q-table title="Treats" :rows="rows" :columns="columns" row-key="name" class="q-mt-md">
    <template v-slot:top>
      <q-item>
        <q-item-section>
          <q-icon
            class="q-pt-md"
            name="fa fa-shopping-cart"
            color="blue"
            size="3rem"
          />
        </q-item-section>
        <q-item-section>
          <q-item-label class="text-h5">Latest Sales</q-item-label>
        </q-item-section>
      </q-item>
    </template>
    <template v-slot:body="props">
      <q-tr :props="props">
        <q-td key="product" :props="props">
          <q-item>
            <q-item-section>
              <q-avatar>
                <q-img :src="props.row.product_img" />
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ props.row.product_number }}</q-item-label>
              <q-item-label>{{ props.row.product_name }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-td>
        <q-td key="buyer" :props="props">
          <q-item>
            <q-item-section>
              <q-avatar color="primary" text-color="white">
                <q-img :src="props.row.buyer_img" />
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ props.row.buyer_name }}</q-item-label>
              <q-item-label caption>{{
                props.row.buyer_caption1
              }}</q-item-label>
              <q-item-label caption>{{
                props.row.buyer_caption2
              }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-td>
        <q-td key="total" :props="props" class="text-center">
          <p class="text-bold text-body2">
            {{ props.row.amount }}
          </p>
        </q-td>
        <q-td key="status" :props="props">
          <q-chip
            class="text-center"
            :color="props.row.status_color"
            text-color="white"
            :label="props.row.status"
          />
        </q-td>
        <q-td key="stock" :props="props">
          <q-item class="text-center">
            <q-item-section>
              <q-item-label>
                {{ props.row.stock }}
              </q-item-label>
              <q-linear-progress
                rounded
                size="4px"
                value="progress"
                :color="props.row.progress_color"
                class="q-mt-sm"
                :style="'width:' + props.row.progress_width"
              />
            </q-item-section>
          </q-item>
        </q-td>
      </q-tr>
    </template>
  </q-table>
</template>

<script>
const columns = [
  {
    name: "product",
    required: true,
    label: "Products",
    align: "left",
    field: (row) => row.name,
    format: (val) => `${val}`,
    sortable: true,
  },
  {
    name: "buyer",
    align: "left",
    label: "Buyer",
    field: "buyer",
    sortable: true,
  },
  { name: "total", label: "Total", field: "total", sortable: true },
  { name: "status", align: "center", label: "status", field: "status", sortable: true },
  { name: "stock", align: "center", label: "Stock", field: "stock", sortable: true },
];

const rows = [
  {
    product_img:
      "https://images.unsplash.com/photo-1553062407-98eeb64c6a62?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=387&q=80",
    product_number: "QWE495",
    product_name: "Men Bag",
    buyer_img:
      "https://pbs.twimg.com/profile_images/1446360024289325063/zl9BZTx-_400x400.png",
    buyer_name: "Ali",
    buyer_caption1: "Purchased date:",
    buyer_caption2: "22 Feb 2022",
    amount: "$2000",
    status: "Canceled",
    status_color: "red-10",
    stock: "15/20",
    progress_color: "blue",
  },
  {
    product_img:
      "https://images.unsplash.com/photo-1621570168855-e9651220e831?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80",
    product_number: "Hp 850",
    product_name: "Laptop",
    buyer_img:
      "https://pbs.twimg.com/profile_images/1433468735331962881/Xtjqc9eg_400x400.jpg",
    buyer_name: "Shakeel Ahmad",
    buyer_caption1: "Purchased date:",
    buyer_caption2: "25 Feb 2022",
    amount: "$4000",
    status: "Delivered",
    status_color: "green",
    stock: "20/50",
    progress_width: "60%",
    progress_color: "red-10",
  },
  {
    product_img:
      "https://rukminim1.flixcart.com/image/416/416/khtghow0-0/kit/e/a/p/plastic-bat-ball-plastic-bat-for-tennis-ball-plastic-bat-ball-original-imafxqtcegpnhhnh.jpeg?q=70",
    product_number: "Quality Bat",
    product_name: "Cricket kit",
    buyer_img:
      "https://pbs.twimg.com/profile_images/1386618778318950400/nrIMoNnr_400x400.jpg",
    buyer_name: "Tanveer Ahmad",
    buyer_caption1: "Purchased date:",
    buyer_caption2: "29 Feb 2022",
    amount: "$1500",
    status: "Pending",
    status_color: "warning",
    stock: "20/50",
  },
  {
    product_img:
      "https://www.bikebound.com/wp-content/uploads/2021/06/Honda-CG125-Tracker-1.jpg",
    product_number: "CG 125",
    product_name: "Bike",
    buyer_img:
      "https://pbs.twimg.com/profile_images/1350679365395341312/2NgqsUxI_400x400.jpg",
    buyer_name: "Abdul Waheed",
    buyer_caption1: "Purchased date:",
    buyer_caption2: "26 Feb 2022",
    amount: "$1700",
    status: "Paid",
    status_color: "cyan-6",
    stock: "75/100",
    progress_width: "80%",
    progress_color: "green",
  },
];

export default {
  props: ["table"],
  setup() {
    return {
      columns,
      rows,
    };
  },
};
</script>

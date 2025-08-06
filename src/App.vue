<script setup>
import { ref } from 'vue';
const drinkMenu = ref([
  { id: '001', name: '珍珠奶茶', intro: '香濃奶茶搭配QQ珍珠', price: 50, stock: 20 },
  { id: '002', name: '冬瓜檸檬', intro: '清新冬瓜配上新鮮檸檬', price: 45, stock: 18 },
  { id: '003', name: '翡翠檸檬', intro: '綠茶與檸檬的完美結合', price: 55, stock: 34 },
  { id: '004', name: '四季春茶', intro: '香醇四季春茶，回甘無比', price: 45, stock: 10 },
  { id: '005', name: '阿薩姆奶茶', intro: '阿薩姆紅茶搭配香醇鮮奶', price: 50, stock: 25 },
  { id: '006', name: '檸檬冰茶', intro: '檸檬與冰茶的清新組合', price: 45, stock: 20 },
  { id: '007', name: '芒果綠茶', intro: '芒果與綠茶的獨特風味', price: 55, stock: 18 },
  { id: '008', name: '抹茶拿鐵', intro: '抹茶與鮮奶的絕配', price: 60, stock: 20 }
])
</script>

<template>
  <main class="p-3 h-screen bg-neutral-100">
    <div class="grid grid-cols-4 gap-2">
      <nav class=" rounded-l-xl col-span-1 bg-gray-200">
        <ul class="p-3">
          <li>Home</li>
          <li class="text-blue-600">第一週作業</li>
          <li>第二週作業</li>
          <li>第三週作業</li>
        </ul>
      </nav>
      <table class=" table-auto rounded-r-xl col-span-3">
        <thead>
          <tr>
            <th scope="col" >品項</th>
            <th scope="col" >描述</th>
            <th scope="col" >價格</th>
            <th scope="col" >庫存</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in drinkMenu" :key="item.id">
            <td class="text-center">{{ item.name }}</td>
            <td ><small>{{ item.intro }}</small></td>
            <td class="text-center">NT$ {{ item.price }}</td>
            <td class="text-center">
              <button @click="item.stock --" :disabled="item.stock <= 0" class="m-1 py-1 px-3 bg-sky-500 hover:bg-sky-700 rounded-full text-white cursor-pointer">-</button>
              {{ item.stock }}<button @click="item.stock ++" class="m-2 py-1 px-3 bg-sky-500 hover:bg-sky-700 rounded-full text-white cursor-pointer">+</button></td>
          </tr>
        </tbody>
      </table>
    </div>
  </main>
</template>
<script setup lang="ts">
import AppLayout from '@/layouts/AppLayout.vue';
import { type BreadcrumbItem } from '@/types';
import { Head } from '@inertiajs/vue3';
import PlaceholderPattern from '../components/PlaceholderPattern.vue';

const breadcrumbs: BreadcrumbItem[] = [
    {
        title: 'Dashboard',
        href: '/dashboard',
    },
];
const transactions = [
  {
    id: 'AAPS0L',
    company: 'Chase & Co.',
    share: 'CAC',
    commission: '+$4.37',
    price: '$3,509.00',
    quantity: '12.00',
    netAmount: '$4,397.00',
  },
  // More transactions...
]
</script>

<template>
    <Head title="Dashboard" />

    <AppLayout :breadcrumbs="breadcrumbs">
  <div class="px-4 sm:px-6 lg:px-8">
    <div class="sm:flex sm:items-center">
      <div class="sm:flex-auto">
        <h1 class="text-base font-semibold text-gray-900">Transactions</h1>
        <p class="mt-2 text-sm text-gray-700">A table of placeholder stock market data that does not make any sense.</p>
      </div>
      <div class="mt-4 sm:mt-0 sm:ml-16 sm:flex-none">
        <button type="button" class="block rounded-md bg-indigo-600 px-3 py-2 text-center text-sm font-semibold text-white shadow-xs hover:bg-indigo-500 focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Export</button>
      </div>
    </div>
    <div class="mt-8 flow-root">
      <div class="-mx-4 -my-2 overflow-x-auto sm:-mx-6 lg:-mx-8">
        <div class="inline-block min-w-full py-2 align-middle sm:px-6 lg:px-8">
          <table class="min-w-full divide-y divide-gray-300">
            <thead>
              <tr>
                <th scope="col" class="py-3.5 pr-3 pl-4 text-left text-sm font-semibold whitespace-nowrap text-gray-900 sm:pl-0">Transaction ID</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Company</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Share</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Commision</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Price</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Quantity</th>
                <th scope="col" class="px-2 py-3.5 text-left text-sm font-semibold whitespace-nowrap text-gray-900">Net amount</th>
                <th scope="col" class="relative py-3.5 pr-4 pl-3 whitespace-nowrap sm:pr-0">
                  <span class="sr-only">Edit</span>
                </th>
              </tr>
            </thead>
            <tbody class="divide-y divide-gray-200 bg-white">
              <tr v-for="transaction in transactions" :key="transaction.id">
                <td class="py-2 pr-3 pl-4 text-sm whitespace-nowrap text-gray-500 sm:pl-0">{{ transaction.id }}</td>
                <td class="px-2 py-2 text-sm font-medium whitespace-nowrap text-gray-900">{{ transaction.company }}</td>
                <td class="px-2 py-2 text-sm whitespace-nowrap text-gray-900">{{ transaction.share }}</td>
                <td class="px-2 py-2 text-sm whitespace-nowrap text-gray-500">{{ transaction.commission }}</td>
                <td class="px-2 py-2 text-sm whitespace-nowrap text-gray-500">{{ transaction.price }}</td>
                <td class="px-2 py-2 text-sm whitespace-nowrap text-gray-500">{{ transaction.quantity }}</td>
                <td class="px-2 py-2 text-sm whitespace-nowrap text-gray-500">{{ transaction.netAmount }}</td>
                <td class="relative py-2 pr-4 pl-3 text-right text-sm font-medium whitespace-nowrap sm:pr-0">
                  <a href="#" class="text-indigo-600 hover:text-indigo-900"
                    >Edit<span class="sr-only">, {{ transaction.id }}</span></a
                  >
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
    </AppLayout>
</template>

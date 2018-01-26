<template>
<div>
<b-navbar toggleable="md" type="dark" variant="info">

  <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

  <b-navbar-brand href="#">سامانه فروش صنایع دستی</b-navbar-brand>

  <b-collapse is-nav id="nav_collapse">

    <b-navbar-nav class="ml-auto">

      <b-nav-form>
        <b-form-input size="sm" class="mr-sm-2" type="text" placeholder="جستجو"/>
        <b-button size="sm" class="my-2 my-sm-0" type="submit">جستجو</b-button>
      </b-nav-form>

      <b-nav-item-dropdown text="زبان" left>
        <b-dropdown-item href="#">EN</b-dropdown-item>
        <b-dropdown-item href="#">ES</b-dropdown-item>
        <b-dropdown-item href="#">RU</b-dropdown-item>
        <b-dropdown-item href="#">FA</b-dropdown-item>
      </b-nav-item-dropdown>

      <b-nav-item-dropdown left>
        <!-- Using button-content slot -->
        <template slot="button-content">
          <em>کاربر</em>
        </template>
        <b-dropdown-item href="#">پروفایل</b-dropdown-item>
        <b-dropdown-item href="#">خروج</b-dropdown-item>
      </b-nav-item-dropdown>
    </b-navbar-nav>

  </b-collapse>
</b-navbar>
<b-container  class="p-4">
  <b-card-group deck class="mb-3">
    <div v-for="p in products" :key=" p._id ">
        <b-card  
          :title='p.name'
          :img-src="'/photos/' + p._id + '.jpg'"
          img-alt="Image"
          img-top
          tag="article"
          style="max-width: 20rem;"
          class="mb-2">
          <p class="card-text">
          {{p.text}}
          </p>
        <b-button href="#" variant="primary">خرید</b-button>
      </b-card>
  </div>
</b-card-group>
</b-container>

</div>
</template>

<script>
import {products} from '~/api/db'
export default {

    data() {
      console.log(products)
        return {
            products: products
            
        }
    }

}
</script>
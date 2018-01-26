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
<b-container>
  <br>
        <b-card class="mx-auto text-center" :title=product.name >
            <b-img :src="'/photos/' + product._id + '.jpg'" rounded="circle"  width="275" height="275" alt="img" class="m-1" />
        <p class="card-text" >
           {{product.text}}
           <br>
           {{product.description}}
        </p>
        </b-card>
</b-container>
    </div>
</template>

<script>
import {products} from '~/api/db'
export default {

    data() {
        return {
            products: products,
            product: products[this.$route.params.id -1]
        }
    }

}
</script>
<template>
  <header class="hl_header nav-shrink ">
    <div class="container-fluid">
      <a class="account-selector">
        <div class="filter-option">
            <div class="filter-option-inner">
                Converse Store #32
            </div>
        </div>
      </a>
      <div class="hl_header--controls">
        <a href="#" class="btn btn-circle btn-yellow hl_header--recent-activities -notification" id="recent_activities-toggle">
            <i class="icon-list"></i>
            <span class="sr-only">View Recent Activities</span>
        </a>
        <a href="#" class="btn btn-circle btn-primary hl_header--copy-link" data-toggle="modal" data-target="#review-link--modal">
            <i class="icon-link"></i>
            <span class="sr-only">Copy Review Link</span>
        </a>
        <div class="hl_header--dropdown hl_header--phone dropdown --no-caret show">
            <a href="#" class="dropdown-toggle" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
                <span class="btn btn-circle btn-green-lt">
                    <svg class="svg-inline--fa fa-phone svg-15" aria-hidden="true" data-prefix="fas" data-icon="phone" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" data-fa-i2svg="">
                        <path fill="currentColor" d="M493.4 24.6l-104-24c-11.3-2.6-22.9 3.3-27.5 13.9l-48 112c-4.2 9.8-1.4 21.3 6.9 28l60.6 49.6c-36 76.7-98.9 140.5-177.2 177.2l-49.6-60.6c-6.8-8.3-18.2-11.1-28-6.9l-112 48C3.9 366.5-2 378.1.6 389.4l24 104C27.1 504.2 36.7 512 48 512c256.1 0 464-207.5 464-464 0-11.2-7.7-20.9-18.6-23.4z">
                        </path>
                    </svg>
                </span>
            </a>
        </div>
        <a href="#" class="hl_header--avatar" role="button">
            <div class="avatar">
                <div class="avatar_img">
                <img src="~/assets/img/img-avatar-sample1.png" alt="Avatar Name">
                </div>
            </div>
        </a>
      </div>
    </div>
  </header>
</template>

<script>
export default {
    data :()=>{
        return {
            
        }
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
    .svg-15{
        height: 15px;
        width: 15px;
    }
</style>
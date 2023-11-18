<template>
  <header>
    <nav>
      <div class="container-fluid text-white pt-5 pb-3">
        <div class="row g-5">
          <div class="col-1"></div>
          <div class="col-11">
            <!-- Nav tabs -->
            <ul class="nav ms-3 ps-3">
              <li class="me-4">
                <button>Now</button>
              </li>
              <li class="me-4">
                <button>Hourly</button>
              </li>
              <li class="me-3 active">
                <button>10 Days</button>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </header>
</template>

<style lang="scss">
.nav {
  width: fit-content;
  padding-bottom: 10px;
  border-bottom: 3px solid rgb(255, 255, 255, 50%);
}
.nav button {
  background-color: transparent;
  color: #fff;
  border: none;
}
.nav li.active {
  position: relative;
}
.nav li.active button {
  font-weight: 700;
  font-size: 17px;
}
.nav li.active::after {
  background-color: #fff;
  content: '';
  width: 90px;
  height: 3px;
  position: absolute;
  bottom: -13px;
  left: 0;
  z-index: 1;
}
</style>

<template>
  <main>
    <section>
      <div class="container-fluid py-5">
        <div class="row">
          <div class="col-12 col-md-1">arrows</div>
          <div class="col-12 col-md-11">
            <div class="container-fluid">
              <h1 class="text-white fs-3 mb-3">10 Days Weather</h1>
              <div class="row g-3">
                <div
                  class="col-6 col-md-4 col-lg-3 col-xxl-2"
                  v-for="(card, index) in 7"
                  :key="index"
                >
                  <div class="card">
                    <!--card-header-->
                    <div
                      class="card-header d-flex align-items-center justify-content-between"
                      data-bs-toggle="modal"
                      data-bs-target="#exampleModal"
                    >
                      <div>
                        <span class="day me-1 fw-bold fs-5 text-secondary"> MONDAY </span>
                        <span class="date opacity-75 fs-6"> 11/6/23 </span>
                      </div>
                      <div>
                        <img
                          src="/right-arrow.svg"
                          alt="right-arrow"
                          width="15"
                          height="13"
                          class="me-1"
                        />
                      </div>
                    </div>

                    <!--card-body-->
                    <div class="card-body">
                      <div class="container-fluid">
                        <div class="row pb-3">
                          <div class="col-8">
                            <div class="day-info">
                              <span class="fw-bold text-muted-main">DAY</span>
                              <h3 class="fs-2 text-secondary mb-0">75*</h3>
                              <span class="fw-bold text-secondary">Sunny </span>
                            </div>
                          </div>
                          <div class="col-4 d-flex align-items-center justify-content-center">
                            <div>
                              <img
                                src="/sun.webp"
                                alt="sun"
                                width="70"
                                height="70"
                                class="rounded-circle weather-img"
                              />
                            </div>
                          </div>
                        </div>

                        <div class="row pt-3 border-top">
                          <div class="col-8">
                            <div class="day-info">
                              <span class="fw-bold text-muted-main">DAY</span>
                              <h3 class="fs-2 text-secondary mb-0">75*</h3>
                              <span class="fw-bold text-secondary">Sunny </span>
                            </div>
                          </div>
                          <div class="col-4 d-flex align-items-center justify-content-center">
                            <div>
                              <img
                                src="/sun.webp"
                                alt="sun"
                                width="70"
                                height="70"
                                class="rounded-circle weather-img"
                              />
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>

                    <!--card-footer-->
                    <div
                      class="card-footer d-flex align-items-center justify-content-center fw-bold"
                    >
                      <i class="bi bi-clock me-1"></i>
                      <span class="text-muted-main"> Hourly </span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Modal -->
        <div
          class="modal fade"
          id="exampleModal"
          tabindex="-1"
          aria-labelledby="exampleModalLabel"
          aria-hidden="true"
        >
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
                <button
                  type="button"
                  class="btn-close"
                  data-bs-dismiss="modal"
                  aria-label="Close"
                ></button>
              </div>
              <div class="modal-body">...</div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
                  Close
                </button>
                <button type="button" class="btn btn-primary">Save changes</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

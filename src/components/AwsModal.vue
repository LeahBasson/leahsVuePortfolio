<template>
    <div class="modal fade" id="awsModal" tabindex="-1" aria-labelledby="awsModalLabel" aria-hidden="true">
      <div class="modal-dialog modal-dialog-centered">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="awsModalLabel">AWS Certificates</h5>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <h5>Computer Foundations</h5>
            <div class="aws-certificates">
                <div class="left-content">
                <h2>1st</h2>
            </div>
            <div class="middle-content">
                <h2>2nd</h2>
            </div>
            <div class="right-content">
                <h2>3rd</h2>
            </div>
            </div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
</template>

<style>
.aws-certificates{
    display: flex;
    justify-content: center;
    gap: 0.9rem;
}

.left-content{
    width: 40rem;
    background-color: pink;
}

.right-content{
    width: 40rem;
    background-color: blueviolet;
}

.middle-content{
    width: 40rem;
    background-color: blue;
}

.modal-title{
    color: var(--primary);
    font-family: "Poppins", sans-serif;
}

.modal-body h5{
    color: var(--primary);
    font-family: "Poppins", sans-serif;
    text-align: left;
}
</style>
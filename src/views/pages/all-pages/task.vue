<script src="../../../../../../../../../Users/mbp/Downloads/newtek/newtek-admin/vue.config.js"></script>


<template>
  <div>
    <Layout>
      <PageHeader :items="items" />

      <div class="d-flex justify-content-between" v-if="!editing">
        <h5 style="margin-bottom: 20px" @click="startEditing"> <i class="ri-flag-fill ps"></i> {{ title }}</h5>
        <div>
          <button class="btn title-cancelbtn text-white mx-2">Cancel Task</button>
          <button class="btn title-savebtn text-white mx-1">Save Task</button>
        </div>
      </div>
      <div class="d-flex align-items-center  gap-3" v-else>
        <input class="form-control w-50 " type="text" v-model="editedTitle" style="margin-bottom: 10px">
        <div>
          <button class="btn text-white mx-2 title-savebtn" @click="save">Save</button>
          <button class="btn text-white light mx-1 title-cancelbtn" @click="cancel">Cancel</button>


        </div>
      </div>

      <div class="d-flex" style="gap:50px">
        <div>
          <p>Abc Project</p>
        </div>
        <div class="d-flex" style="gap:10px">
          <label style="color:#434445;">Milestone</label>
          <b-form-checkbox v-model="checked" switch class="mb-1"></b-form-checkbox>
        </div>

      </div>
      <div class="row">
        <div class="col-lg-7">
          <div class="card">
            <div class="card-body">
              <div class="mt-1">
                <h5 class="font-size-14">Task Description</h5>
                <textarea id="abc" name="abc" rows="4" cols="50" class="form-control"></textarea>
              </div>
              <div class="row mt-3">
                <div class="col-lg-6">
                  <div class="mt-4">
                    <h5 class="font-size-14">Start Date</h5>
                    <b-form-input id="date" value="2019-08-19" type="date"></b-form-input>
                  </div>
                  <div class="mt-4" v-if="!checked">
                    <h5 class="font-size-14">Duration</h5>
                    <b-form-input id="text" value="06 Days" type="text"></b-form-input>
                  </div>
                </div>
                <div class="col-lg-6">
                  <div class="mt-4">
                    <h5 class="font-size-14" v-if="!checked">End Date</h5>

                    <h5 class="font-size-14" v-else>Due Date</h5>
                    <b-form-input id="date" value="2019-08-19" type="date"></b-form-input>
                  </div>


                  <div class="mt-4" v-if="!checked">
                    <h5 class="font-size-14">Assignee</h5>
                    <div class="customSelect">
                      <select name="status" id="" class="form-control">
                        <option value="">Select</option>
                        <option value="active">Active</option>
                        <option value="inactive">InActive</option>
                      </select>
                    </div>
                  </div>

                </div>
                <div class="col-lg-12" v-if="checked">

                  <div class="mt-4">
                    <h5 class="font-size-14">Assignee</h5>
                    <div class="customSelect">
                      <select name="status" id="" class="form-control">
                        <option value="">Select</option>
                        <option value="active">Active</option>
                        <option value="inactive">InActive</option>
                      </select>
                    </div>
                  </div>
                </div>
                <div class="col-lg-6">

                  <div class="mt-4">
                    <h5 class="font-size-14">Status</h5>

                    <div class="customSelect">
                      <select name="status" id="" class="form-control">
                        <option value="select">Select</option>
                        <option value="active">Active</option>
                        <option value="inactive">InActive</option>
                      </select>
                    </div>

                  </div>
                </div>


                <div class="col-lg-6">
                  <div class="mt-4">
                    <div class="d-flex align-items-center justify-content-between">
                      <div>
                        <h5 class="font-size-14">Progress</h5>
                      </div>
                      <div style="width:100px">
                        <input class="form-control" type="number" id="progressInput" v-model="progressValue"
                          @input="updateProgressBar" min="0" max="100" style="height:40px;border-radius:10px">
                      </div>

                    </div>

                    <div class="progress mt-3" :style="{ borderRadius: '10px', color: '#104062' }">
                      <div class="progress-bar" role="progressbar"
                        :style="{ background: '#104062', width: progressValue + '%' }" :aria-valuenow="progressValue"
                        aria-valuemin="0" aria-valuemax="100">
                      </div>
                    </div>

                  </div>
                </div>


              </div>

            </div>
          </div>

          <div class="row">
            <div class="col-6">
              <div class="card">
                <div class="card-body">
                  <div class="d-flex align-items-center " style="gap:30px">
                    <div>
                      <h5 class="font-size-14 text-dark ">Parent Tasks</h5>
                    </div>
                    <div style="flex:1">
                      <div class="customSelect">
                        <select name="status" id="" class="form-control">
                          <option> Project Initialization</option>
                          <option>Update Home Screen</option>
                          <option>Fixes on Sidebar Panel</option>
                        </select>
                      </div>
                    </div>

                  </div>

                </div>
              </div>
            </div>
            <div class="col-6">
              <div class="card">
                <div class="card-body">
                  <div class="d-flex justify-content-between">

                    <h5 class="font-size-14 text-dark go">Dependecies

                      <i data-title="Dependencies can be changed from giant chart" class="ri-error-warning-fill alert-icon"></i>
                    </h5>
                    <div>
                      <ul class="dep-list">
                        <li>ABC Tasks Transfer</li>
                        <li>Task 1</li>
                        <li>Task 2</li>
                        <li>Task 3</li>
                      </ul>
                    </div>

                  </div>
                  <div class="row mt-3">
                    <div class="col-lg-6">
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-lg-5">
          <div class="row">
            <div class="col-12" style="margin-bottom: 20px">

              <div class="file-upload">
                <div class=' h-100 d-flex justify-content-center align-items-center'>
                  <div class="d-flex upd-doc">
                    <label for="file-input">Upload Document</label>
                    <small style="color:#949699;font-size:14px;">File size to 20 mb (jpg, png, pdf) </small>
                  </div>
                </div>
                <input type="file" id="file-input">
              </div>
            </div>

            <div class="col-12">
              <!-- <div class=""> -->

              <!-- </div> -->
              <div class="card">
                <div class="card-body">
                  <div class="d-flex my-2 justify-content-between align-items-center border-bottom ">
                    <div class="d-flex file-up">
                      <div>
                        <i class="ri-attachment-2 file-icon"></i>
                      </div>
                      <div>
                        <p class="mt-2">File1.pdf</p>
                      </div>
                    </div>

                    <button class="btn del-btn btn-primary mx-2 px-2 py-1"> <i class="ri-delete-bin-line"
                        style="font-size:20px"></i> </button>
                  </div>

                  <div class="row mt-3">
                    <div class="col-lg-6">
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-12">
              <div class="card">
                <div class="card-body">
                  <div class="d-flex justify-content-between align-items-center ">
                    <h5 class="font-size-16 text-dark ">Comments</h5>
                    <span @click="toggleComment" > 
                      <i v-if="!commentView" class="ri-eye-line eye-icon "></i>
                      <i v-else class="ri-eye-off-line eye-icon cursor-pointer"></i>
                    </span>
                  </div>
                  <div v-if="commentView" > 
                  <div class="comment">
                    <div class="d-flex justify-content-between" >
                    <div class="comment-header "> 
                      <img src="../../../assets/images/users/avatar-2.jpg" alt="Candidate Image">
                      <div class="candidate-name">John Doe</div>
                    </div>
                      <div class="comment-date ">July 30, 2023</div>
                    </div>
                    <div class="comment-description">
                      Please review this section of code for potential improvements or optimizations.
                    </div>
                  </div>
                  <div class="comment">
                    <div class="d-flex justify-content-between" >
                    <div class="comment-header "> 
                      <img src="../../../assets/images/users/avatar-3.jpg" alt="Candidate Image">
                      <div class="candidate-name">Alex Fay</div>
                    </div>
                      <div class="comment-date ">July 31, 2023</div>
                    </div>
                    <div class="comment-description">
                      This function is no longer in use and can be safely removed.
                    </div>
                  </div>
                </div>
                </div>
              </div>
            </div>
            <div class="col-12">
              <div class="card">
                <div class="card-body">
                  <div class="d-flex justify-content-between align-items-center ">
                    <h5 class="font-size-16 text-dark ">History</h5>
                    <span class="cursor-pointer px-1" @click="toggleHistory">
                      <i v-if="historyView" class="ri-eye-line eye-icon "></i>
                      <i v-else class="ri-eye-off-line eye-icon cursor-pointer"></i>
                    </span>
                  </div>
                  <div v-if="!historyView" class="row mt-3">
                    <div class="d-flex justify-content-between w-100 px-3" style="color:#104062;font-weight:600;">
                      <p>JM Created the Task</p>
                      <p>22th-January-2023</p>
                    </div>
                    <div class="d-flex justify-content-between w-100 px-3" style="color:#104062;font-weight:600;">
                      <p>MA Changes Task status</p>
                      <p>22th-January-2023</p>
                    </div>

                  

                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Layout>

  </div>
</template>



<script>
import Layout from "../../layouts/main";
import PageHeader from "@/components/page-header";
import user1 from '../../../assets/images/users/avatar-2.jpg'
/**
 * Starter page component
 */
export default {
    page: {
        title: "Task",
        meta: [{
            name: "description"
        }]
    },
    components: {
        Layout,
        PageHeader
    },
    data() {
        return {
          checked:   false ,
          historyView: false ,
          commentView : false ,
          progressValue: 25,
            title: 'Title',
    editedTitle: '',
    editing: false , 
    userImg: user1
        };
    },
    methods: {
      
      toggleComment() {
        this.commentView = !this.commentView
      },
      toggleHistory() {
        this.historyView = !this.historyView
      },
      toggleCheckbox() {
      this.checked = !this.checked; // Toggle the checkbox state
    },
        updateProgressBar() {
            this.progressValue = Math.max(0, Math.min(this.progressValue, 100));
        },
        startEditing() {
      this.editing = true;
      this.editedTitle = this.title;
    },
    save() {
      this.title = this.editedTitle;
      this.editing = false;
    },
    cancel() {
      this.editing = false;
    }
    }
};
</script>
<style  >
i[data-title]:hover::after {
  content: attr(data-title);
  position: absolute;
  background-color: #104062;
  font-weight: 100;
  font-family: Arial, Helvetica, sans-serif;
  color: white;
  padding: 5px;
  border-radius: 4px;
  left: 50%;
  font-size: small;
  transform: translateX(-10%);
  transform: translateX(-15%);
  white-space: wrap;
}

.b-avatar-group {
    position: initial !important;
    margin-bottom: 10px !important;
}
.comment {
  margin-top: 10px;
  box-shadow: rgba(0, 0, 0, 0.1) 1px 0px 11px -2px;
  padding: 5px;

}

.comment-header {
  display: flex;
  align-items: center;
  flex-direction: row;
}

.comment-header img {
  width: 35px;
  height: 35px;
  border-radius: 50%;
  margin-right: 10px;
}

.candidate-name {
  font-weight: bold;
  margin-right: 10px;
  font-size: medium;
}

.comment-date {
  color: gray;
  margin: 10px 5px;
  font-size: small;
  font-weight: bold;
}

.comment-description {
  margin-top: 5px;
  /* Add your desired styles for the comment description here */
}
</style>
<style>
.file-icon {

  color: #104062 !important;
  font-size: 27px;
}

.file-up {
  /* border: 1px solid #ced4da !important; */
  width: 100%;
  /* height: 40px !important; */
  border-radius: 5px;
  display: flex;
  align-items: center;
  gap: 14px;
  padding-left: 10px;
  padding-top: 4px;
}

.upd-doc {
  flex-direction: column;
}

input[type="file"] {
  display: none;
}

/* Style the wrapper div */
.file-upload {
  display: inline-block;
  position: relative;
  border: 2px dashed #104062;
  background-color: #f1f1f1;
  padding: 10px;
  border-radius: 5px;
  cursor: pointer;
  width: 100%;
  text-align: center;
  height: 250px;
  /* margin-bottom: 20px */
}

/* Style the label text */
.file-upload label {
  font-size: x-large;
  color: #104062;
  font-weight: bolder;
  font-family: 'Arial'
}

/* Show a hover effect */
.file-upload:hover {
  background-color: #e0e0e0;
}

/* Show a focus effect */
.file-upload:focus-within {
  outline: none;
  box-shadow: 0 0 0 2px #007bff;
}

.eye-icon {
  font-size: x-large;
  color: #2B307E !important;
}

::placeholder {
  color: #583D72;

}

.go {
  display: flex;
  height: fit-content;
  align-items: center;
  gap: 6px;
}

.del-btn {
  background: #104062 !important;
  border: none !important
}

.alert-icon {
  font-size: 23px;

}

.dep-list {
  list-style-type: none;
  padding: 0;
}

.card h5 {
  color: #DC3545;
  font-weight: 600;
}

.customSelect {
  position: relative;
  display: -webkit-flex;
  display: flex;
  height: fit-content;
  line-height: 3;
  background: #fff;
  overflow: hidden;
  border-radius: 0.25em;
}

.dep-list li {
  color: #104062;
  text-align: right;
  font-weight: 600;
}


.customSelect::after {
  content: "\ea4c";
  position: absolute;
  top: 0px;
  right: 0;
  padding: 0 1em;
  background: #104062;
  cursor: pointer;
  padding-top: 3px;
  pointer-events: none;
  transition: 0.25s all ease;
  font-family: "remixicon";
  color: white;
  bottom: 0;
}

.form-control {
  height: calc(2.3em + 0.94rem + 2px);
}

.custom-switch .custom-control-label::after {
  background-color: #104062;
}

.title-savebtn {
  background-color: #104062;
}

.title-savebtn:hover {
  background-color: #155786;
}

.title-cancelbtn:hover {
  background-color: rgb(245, 47, 47);
}

.title-cancelbtn {
  background-color: red;
}

.ps {
  color: red;
}

.ps {
  color: red;
}
</style>

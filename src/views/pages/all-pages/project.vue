<script src="../../../../../../../../../Users/mbp/Downloads/newtek/newtek-admin/vue.config.js"></script>
<template>
    <div>
        <Layout>
            <PageHeader :items="items" />
            <div v-if="!editing">
                <div class="d-flex justify-content-between" v-if="!editing">
        <h5 style="margin-bottom: 20px" @click="startEditing"> <i class="ri-flag-fill ps"></i> {{ title }}</h5>
        <div>
          <button class="btn title-cancelbtn text-white mx-2">Cancel Project</button>
          <button class="btn title-savebtn text-white mx-1">Save Project</button>
        </div>
      </div>
      </div>
      <div class="d-flex align-items-center  gap-3" v-else>
        <input class="form-control w-50 " type="text" v-model="editedTitle" style="margin-bottom: 10px">
       <div>
        <button  class="btn text-white mx-2 title-savebtn" @click="save">Save</button>
        <button class="btn text-white light mx-1 title-cancelbtn" @click="cancel">Cancel</button>

        
       </div>
      </div>

            <div class="d-flex mt-2" style="gap:50px">
                <div>
                    <strong><i class="far fa-calendar"></i> 20 june</strong>
                </div>
                <div class="d-flex" style="gap:10px">
                    <label style="color:#434445;"><i class="fas fa-users"></i> 7 Members</label>
                </div>
                <b-avatar-group size="30px">
                    <b-avatar></b-avatar>
                    <b-avatar src="https://placekitten.com/300/300" variant="info"></b-avatar>
                    <b-avatar variant="warning"></b-avatar>
                    <b-avatar src="https://placekitten.com/320/320" variant="dark"></b-avatar>
                </b-avatar-group>

            </div>
            <div class="row">
                <div class="col-lg-8">
                    <div class="card">
                        <div class="card-body">
                            <div class="mt-1">
                                <h5 class="font-size-14">Project Description</h5>
                                <textarea id="abc" name="abc" rows="4" cols="50" class="form-control"></textarea>
                            </div>
                            <div class="row mt-3">
                                <div class="col-lg-4">
                                    <div class="mt-4">
                                        <h5 class="font-size-14">Start Date</h5>
                                        <b-form-input id="date" value="2019-08-19" type="date"></b-form-input>
                                    </div>

                                </div>
                                <div class="col-lg-4">
                                    <div class="mt-4">
                                        <h5 class="font-size-14">End Date</h5>
                                        <b-form-input id="date" value="2019-08-19" type="date"></b-form-input>
                                    </div>

                                </div>
                                <div class="col-lg-4">
                                    <div class="mt-4  go d-flex justify-content-start">
                                        <h5 class="font-size-14 ">Actual End Date</h5>
                                        <i data-title="Calculated from giant chart" class="ri-error-warning-fill alert-icon"></i>


                                    </div>
                                    <b-form-input id="ac" value="2019-08-19" type="date"></b-form-input>

                                </div>
                                <div class="col-lg-3">
                                    <div class="mt-4  go d-flex justify-content-start">
                                        <h5 class="font-size-14 ">Actual Duration</h5>
                                        <i data-title="Calculated from giant chart" class="ri-error-warning-fill alert-icon"></i>


                                    </div>
                                    <b-form-input id="ac" value="320 days" type="text"></b-form-input>

                                </div>


                                <div class="col-lg-3">
                                    <div class="mt-4">
                                        <h5 class="font-size-14">Project Budget </h5>
                                        <b-form-input value="$3000" type="text"></b-form-input>
                                    </div>

                                </div>
                                <div class="col-lg-3">
                                    <div class="mt-4  go d-flex justify-content-start">
                                        <h5 class="font-size-14 ">Consumed Budget</h5>
                                        <i data-title="Calculated from giant chart" class="ri-error-warning-fill alert-icon"></i>


                                    </div>
                                    <b-form-input id="ac" value="$5000" type="text"></b-form-input>

                                </div>
                                <div class="col-lg-3">
                                    <div class="mt-4">
                                        <h5 class="font-size-14">Default View</h5>
                    <div class="customSelect ">
                      <select name="status" id="" class="form-control">
                        <option value="">Giant View</option>
                        <option value="VIEW 2">View 2</option>
                        <option value="VIEW 3">View 3</option>
                      </select>
                    </div>
                                    </div>

                                </div>







                            </div>

                        </div>
                    </div>

                    <div class="card">
                        <div class="card-body">
                            <div class="d-flex align-items-center justify-content-between" style="gap:30px">
                                <div>
                                    <h5 class="font-size-14  ">Project Team</h5>
                                </div>
                                <div>
                                    <button class="btn btn-primary mem-btn">Add member</button>
                                </div>

                            </div>
                            <div class="mt-4">
                                <div class="table-responsive">
                                    <table class="table mb-0">
                                        <thead>
                                            <tr>
                                                <th>Name</th>
                                                <th>Initials</th>
                                                <th>Roles</th>
                                                <th>Actions</th>
                                            </tr>
                                        </thead>
                                        <tbody>
                                            <tr>
                                                <th scope="row">
                                                    <div class="d-flex align-items-center gap-2">
                                                        <div class="mt-4 mt-md-0">
                                                            <img class="rounded-circle avatar-xs" alt="200x200"
                                                                src="@/assets/images/users/victor.png"
                                                                data-holder-rendered="true" />
                                                        </div>
                                                        <h5 class="mx-2 mt-2 text-dark cand-name">Victor Rampling</h5>
                                                    </div>
                                                </th>
                                                <td>Vra</td>
                                                <td>Project Manager</td>
                                                <td>
                                                    <div class="del_space">
                                                        <img class="del-icon" src="@/assets/images/users/delete.png" alt="">
                                                    </div>
                                                </td>
                                            </tr>
                                            <tr>
                                                <th scope="row">
                                                    <div class="d-flex align-items-center gap-2">
                                                        <div class="mt-4 mt-md-0">
                                                            <img class="rounded-circle avatar-xs" alt="200x200"
                                                                src="@/assets/images/users/joan.png"
                                                                data-holder-rendered="true" />
                                                        </div>
                                                        <h5 class="mx-2 mt-2 text-dark cand-name">Joan Dyer</h5>
                                                    </div>
                                                </th>
                                                <td>Jdy</td>
                                                <td>Team Member</td>
                                                <td>
                                                    <div class="del_space">
                                                        <img class="del-icon" src="@/assets/images/users/delete.png" alt="">
                                                    </div>
                                                </td>
                                            </tr>
                                            <tr>
                                                <th scope="row">
                                                    <div class="d-flex align-items-center gap-2">
                                                        <div class="mt-4 mt-md-0">
                                                            <img class="rounded-circle avatar-xs" alt="200x200"
                                                                src="@/assets/images/users/sally.png"
                                                                data-holder-rendered="true" />
                                                        </div>
                                                        <h5 class="mx-2 mt-2 text-dark cand-name">Sally Graham</h5>
                                                    </div>
                                                </th>
                                                <td>Sgr</td>
                                                <td>Team Member</td>
                                                <td>
                                                    <div class="del_space">
                                                        <img class="del-icon" src="@/assets/images/users/delete.png" alt="">
                                                    </div>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </div>
                            </div>

                        </div>



                    </div>
                </div>
                <div class="col-lg-4">
                    <div class="row">

                        <div class="col-12">
                            <div class="card p-3">
                                <div class="row">
                                    <div class="col-3">
                                        <div class="health_heart">
                                            <img src="@/assets/images/users/heart.png" alt="">
                                        </div>
                                    </div>
                                    <div class="col-9 ">
                                        <h5 class="text-dark font-size-14">Projects Overall Health</h5>
                                        <div class="health">
                                            <div class="radio-container">
                                                <div>
                                                    <label for="th" class="radio-label">
                                                        <img class="health-icon"
                                                            src="@/assets/images/users/cloud-lightning.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="th" name="radio-group" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="th2" class="radio-label">
                                                        <img class="health-icon" src="@/assets/images/users/sun.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="th2" name="radio-group" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="th3" class="radio-label">
                                                        <img class="health-icon" src="@/assets/images/users/cloud.png"
                                                            alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="th3" name="radio-group" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="th4" class="radio-label">
                                                        <img class="health-icon" src="@/assets/images/users/driz.png"
                                                            alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="th4" name="radio-group" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="th5" class="radio-label">
                                                        <img class="health-icon" src="@/assets/images/users/set.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="th5" name="radio-group" value="radio3">
                                                </div>


                                            </div>
                                        </div>
                                    </div>
                                </div>


                            </div>
                        </div>

                        <div class="col-12">
                            <div class="card p-3">
                                <div class="row">
                                    <div class="col-3">
                                        <div class="status_eye">
                                            <img src="@/assets/images/users/eye.png" alt="">
                                        </div>
                                    </div>
                                    <div class="col-9 ">
                                        <h5 class="text-dark font-size-14">Status</h5>
                                        <div class="status">
                                            <div class="radio-container">
                                                <div>
                                                    <label for="not" class="radio-label">
                                                        Not Started
                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="not" name="status" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="active" class="radio-label">
                                                        Active

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="active" name="status" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="hold" class="radio-label">
                                                        On Hold

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="hold" name="status" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="close" class="radio-label">
                                                        Closed
                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="close" name="status" value="radio3">
                                                </div>


                                            </div>

                                        </div>
                                    </div>
                                </div>


                            </div>
                        </div>
                        <div class="col-12">
                            <div class="card p-3">
                                <div class="row">
                                    <div class="col-3">
                                        <div class="dollar">
                                            <img src="@/assets/images/users/dollar-sign.png" alt="">
                                        </div>
                                    </div>
                                    <div class="col-9 ">
                                        <h5 class="text-dark font-size-14">Cost Trend</h5>
                                        <div class="trend">
                                            <div class="radio-container">
                                                <div>
                                                    <label for="up" class="radio-label">
                                                        <img class="trend-icon"
                                                            src="@/assets/images/users/up.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="up" name="cost" value="radio3">
                                                </div>


                                            </div>
                                           
                                            <div class="radio-container">
                                                <div>

                                                    <label for="right" class="radio-label">
                                                        <img class="trend-icon" src="@/assets/images/users/right.png"
                                                            alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="right" name="cost" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="down" class="radio-label">
                                                        <img class="trend-icon" src="@/assets/images/users/down.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="down" name="cost" value="radio3">
                                                </div>


                                            </div>
                                            
                                        </div>
                                    </div>
                                </div>


                            </div>
                        </div>
                        <div class="col-12">
                            <div class="card p-3">
                                <div class="row">
                                    <div class="col-3">
                                        <div class="calendar">
                                            <img src="@/assets/images/users/calendar.png" alt="">
                                        </div>
                                    </div>
                                    <div class="col-9 ">
                                        <h5 class="text-dark font-size-14">Schedule Trend</h5>
                                        <div class="trend">
                                            <div class="radio-container">
                                                <div>
                                                    <label for="up2" class="radio-label">
                                                        <img class="trend-icon"
                                                            src="@/assets/images/users/up.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="up2" name="schedule" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="right2" class="radio-label">
                                                        <img class="trend-icon" src="@/assets/images/users/right.png"
                                                            alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="right2" name="schedule" value="radio3">
                                                </div>


                                            </div>
                                            <div class="radio-container">
                                                <div>

                                                    <label for="down2" class="radio-label">
                                                        <img class="trend-icon" src="@/assets/images/users/down.png" alt="">

                                                    </label>
                                                </div>
                                                <div>
                                                    <input type="radio" id="down2" name="schedule" value="radio3">
                                                </div>


                                            </div>
                                           
                                            
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
            title: "ABC Project",
            progressValue: 25, // Initial progress value (you can change it if you want)
    editedTitle: '',
    editing: false
        };
    },
    methods: {
        updateProgressBar() {
            // Ensure the progressValue is within the valid range (0-100)
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

<style >
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
  transform: translateX(-15%);
  transform: translateY(-80%);
  white-space: nowrap;
}
.b-avatar-group {
    position: initial !important;
    margin-bottom: 10px !important;
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
.health-icon {
    width: 27px !important;
    height: 24px !important;
}

.status_eye {
    background-color: #FFE28C !important;
}
.dollar {
    background-color: #18778B !important;
}
.calendar {
    background-color: #EA8383 !important;
}

.health_heart,
.status_eye  , .dollar , .calendar{
    padding: 25px;
    background-color: #987999;
    display: flex;
    justify-content: center;
    border-radius: 6px;
    height: 75px;
    width: 75px;
}
.trend {
    justify-content: space-between;
    padding: 0px 10px;
}
.trend-icon {
    width: 30px;
    height: 30px;
}
.health_heart img {
    height: 25px;
    width: 25px;
    position: relative;
}
.dollar img {
    height: 30px;
    width: 30px;
    position: relative;
}
</style>
<style  >
.health,
.status , .trend {
    display: flex;
    margin-top: 10px;
    padding-top: 10px;
    /* border: 2px solid red; */
    gap: 22px;
}

.radio-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    flex-wrap: wrap;
}

.radio-label {
    cursor: pointer;
    font-weight: 900 !important;
}

.radio-label img {
    width: 50px;
    height: 50px;
}


.del_space {
    border: 1px solid #F0F0F0;
    border-radius: 0px, 6px, 6px, 0px;
    display: flex;
    padding: 10px !important;
    width: fit-content;
}

.del-icon {
    width: 15px;
    height: 17px;
}

.cand-name {
    font-size: 14px !important;
}

.mem-btn {
    background-color: #104062 !important;
}

.b-avatar-group {
    position: absolute;
    left: 500px;
    width: 101px;
    top: 149px;

}


.file-icon {

    color: #104062 !important;
    font-size: 27px;
}

.file-up {
    border: 1px solid #ced4da !important;
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
    margin-top: 13px !important;
    gap: 6px;
}

.del-btn {
    background: #104062 !important;
    border: none !important
}

.alert-icon {
    font-size: 22px;

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

.ps {
    color: red;
}</style>

<template>

    <div>

        <!-- NAVBAR -->
        <nav class="navbar navbar-dark bg-dark">
            <div class="container-fluid">

                <select class="form-select w-auto" v-model="currentSection">
                    <option value="requirements">0. Requirements</option>
                    <option value="coins">1. Coins Registration</option>
                    <option value="usdc">2. Obtaining USDC</option>
                    <option value="acccat">3. ACCCAT Registration</option>
                    <option value="recharge">4. Recharge Account</option>
                </select>

                <button class="btn btn-danger btn-sm" @click="logout">
                    Logout
                </button>

            </div>
        </nav>

        <div class="d-flex justify-content-between align-items-center p-3">

            <button class="btn btn-outline-secondary btn-sm" @click="prevSection"
                :disabled="currentSection === sections[0]">
                ← Previous
            </button>

            <strong>
                Step {{ sectionIndex + 1 }} / {{ sections.length }}
            </strong>

            <button class="btn btn-outline-primary btn-sm" @click="nextSection"
                :disabled="currentSection === sections[sections.length - 1]">
                Next →
            </button>

        </div>

        <!-- CONTENT -->
        <div class="container py-3">


            <!-- STEP 0 -->
            <div v-if="currentSection === 'requirements'">

                <div class="accordion" id="accordionExample">
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button bg-danger-subtle" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                                Requirements
                            </button>
                        </h2>
                        <div id="collapseOne" class="accordion-collapse collapse show"
                            data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <ol>
                                    <li class="mb-2">Smartphone (Good condition)</li>
                                    <li class="mb-2">Active Email Address</li>
                                    <li class="mb-2">Active Phone Number</li>
                                    <li class="mb-2">One (1) Valid ID, any of the following:
                                        <ul class="mt-3">
                                            <li class="mb-2">Passport (Philippine or Foreign)</li>
                                            <li class="mb-2">Driver’s License</li>
                                            <li class="mb-2">Philippine Identification System (PhilSys) ID (PVC,
                                                e-PhilSys, Digital)
                                            </li>
                                            <li class="mb-2">Unified Multi-Purpose ID (UMID)</li>
                                            <li class="mb-2">Social Security System (SSS) Card</li>
                                            <li class="mb-2">Professional Regulation Commission (PRC) ID</li>
                                            <li class="mb-2">Postal ID (newly issued)</li>
                                            <li class="mb-2">Voter’s ID or Voter’s Certificate</li>
                                            <li class="mb-2">NBI Clearance</li>
                                        </ul>
                                    </li>
                                </ol>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button collapsed bg-danger-subtle" type="button"
                                data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false"
                                aria-controls="collapseTwo">
                                Applications
                            </button>
                        </h2>
                        <div id="collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <table class="table table-bordered small">
                                    <thead>
                                        <tr>
                                            <th>Application</th>
                                            <th>Purpose</th>
                                            <th>Download Link</th>
                                        </tr>
                                    </thead>
                                    <tbody>
                                        <tr>
                                            <td>Acccat</td>
                                            <td>Coins Mining</td>
                                            <td>Website</td>
                                        </tr>
                                        <tr>
                                            <td>Coins.ph</td>
                                            <td>cryptocurrency transactions</td>
                                            <td>Play Store</td>
                                        </tr>
                                        <tr>
                                            <td>Google Authenticator</td>
                                            <td>will be used in Withdrawal</td>
                                            <td>Play Store</td>
                                        </tr>
                                        <tr>
                                            <td>Whatsapp</td>
                                            <td>Claiming rewards</td>
                                            <td>Play Store</td>
                                        </tr>
                                    </tbody>
                                </table>

                            </div>
                        </div>
                    </div>
                </div>

            </div>


            <!-- STEP 1 -->
            <div v-if="currentSection === 'coins'">

                <div class="accordion" id="accordionExample">
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button  bg-danger-subtle" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                                Create Coins.ph account
                            </button>
                        </h2>
                        <div id="collapseOne" class="accordion-collapse collapse show"
                            data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <ol>
                                    <li>Download <b>Coins.ph</b> app in the App Store or Play Store</li>
                                    <li>Register an account</li>
                                    <li>Input required informations <br>
                                        <b>Note:</b> <br>
                                        You will be asked about your profession,<br>
                                        You can select <b>Self Employed</b> and <b>Other Services</b><br>
                                        For coins usage, select <b>BOTH</b>
                                    </li>
                                </ol>

                                <h6>Make sure the account is <span
                                        class="badge text-bg-light btn-sm text-success">Verified</span> and
                                    has a phone number</h6>
                                <img src="@/assets/images/verified.png" class="img-fluid mt-3  w-75">

                                <p class="mt-5 small">Please check the <b>Unverifed accounts</b> and <b>Phone number
                                        binding</b> for more information</p>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button collapsed  bg-danger-subtle" type="button"
                                data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false"
                                aria-controls="collapseTwo">
                                Unverified accounts
                            </button>
                        </h2>
                        <div id="collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <ul>
                                    <li class="mb-3">Please check the <b>Identity Verification</b> in profile page <br>
                                        <img src="@/assets/images/identity-verification.png"
                                            class="img-fluid mt-3  w-75" size="small">
                                    </li>
                                    <li class="mb-3">Make sure both <b>Basic</b> and <b>Identity Verification</b> is
                                        checked <br>
                                        <img src="@/assets/images/identity-verification2.png"
                                            class="img-fluid mt-3  w-75">
                                    </li>
                                    <li class="mb-3">If both are checked but still <b class="text-danger">UNVERIFIED</b>
                                        or the verification process is pending and taking time.<br>
                                        <b>Contact customer support</b> <br>
                                        <img src="@/assets/images/customer-support.png" class="img-fluid mt-3  w-75">
                                    </li>
                                </ul>

                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button collapsed  bg-danger-subtle" type="button"
                                data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false"
                                aria-controls="collapseThree">
                                Phone number binding
                            </button>
                        </h2>
                        <div id="collapseThree" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <ol>
                                    <li>Go to <b>HOMEPAGE</b></li>
                                    <li>Click the <b>PAY icon</b></li>
                                    <li>Click My <b>Code</b></li>
                                    <li>Enter your <b>phone number</b></li>
                                    <li>Complete the <b>email verification</b></li>

                                </ol>
                                <p>If you're able to <b>Generate a QR Code</b>, it means your number is successfully
                                    bound.</p>
                            </div>
                        </div>
                    </div>
                </div>

            </div>


            <!-- STEP 2 -->
            <div v-if="currentSection === 'usdc'">

                <h5>Two ways to obtain USDC.</h5>

                <div class="small">
                    <strong class="text-danger">Note:</strong>
                    <ol>
                        <li><b>101 USDC</b> is the requirement for a valid USER, and the minimum amount of every events
                        </li>
                        <li><b>30 USDC</b> is the minimum amount to participate in mining</li>
                    </ol>
                </div>

                <div class="accordion" id="accordionExample">
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button bg-danger-subtle" type="button" data-bs-toggle="collapse"
                                data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                                Buying your OWN USDC
                            </button>
                        </h2>
                        <div id="collapseOne" class="accordion-collapse collapse show"
                            data-bs-parent="#accordionExample">
                            <div class="accordion-body">
                                <ol>
                                    <li>First you need to have enough PHP to buy USDC
                                        <ul class="mt-3">
                                            <li class="mb-2">You can cash in to your Coins.ph account through 7-11,
                                                GCash,
                                                Paymaya, or Bank Deposit</li>
                                            <li class="mb-2">Tap <b>PAY</b></li>
                                            <li class="mb-2">Tap <b>My Code</b></li>
                                            <li class="mb-2">Scan the QR Code using your preferred payment method</li>
                                        </ul>
                                    </li>
                                    <li>Once you have enough PHP balance, you can now buy USDC
                                        <ul class="mt-3">
                                            <li class="mb-2">Go to <b>HOME</b></li>
                                            <li class="mb-2">Click <b>Buy/Sell</b></li>
                                            <li class="mb-2">Select <b>Buy USDC</b></li>
                                            <li class="mb-2">Enter <b>USDC amount</b></li>
                                            <li class="mb-2">Review and submit</li>
                                        </ul>
                                    </li>
                                </ol>
                            </div>
                        </div>
                    </div>
                    <div class="accordion-item">
                        <h2 class="accordion-header">
                            <button class="accordion-button collapsed bg-danger-subtle" type="button"
                                data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false"
                                aria-controls="collapseTwo">
                                Call a Friend
                            </button>
                        </h2>
                        <div id="collapseTwo" class="accordion-collapse collapse" data-bs-parent="#accordionExample">
                            <div class="accordion-body">

                                <div class="small">
                                    <strong class="text-danger">Note:</strong>
                                    <ul>
                                        <li>The following steps are for the SENDER of the USDC transfer. The RECEIVER
                                            should just wait for the USDC to arrive and check if the amount is correct.
                                        </li>
                                    </ul>
                                </div>
                                <ol>
                                    <li class="mb-2">Click <b>Portfolio</b></li>
                                    <li class="mb-2">Select <b>USDC</b></li>
                                    <li class="mb-2">Click <b>Withdraw</b></li>
                                    <li class="mb-2">Select <b>Coins Account</b></li>
                                    <li class="mb-2">Switch to <b>Phone tab</b></li>
                                    <li class="mb-2">Enter <b>receiver phone number</b></li>
                                    <li class="mb-2">Enter the <b>USDC amount</b></li>
                                    <li class="mb-2"><b>Verify</b> the transaction via <b>Facial Recognition or SMS and
                                            EMAIL
                                            Verification</b></li>
                                </ol>
                            </div>
                        </div>
                    </div>
                </div>

            </div>


            <!-- STEP 3 -->
            <div v-if="currentSection === 'acccat'">

                <h5>Registering in ACCCAT</h5>

                <ol class="mt-3">
                    <li class="mb-2">Get <b>invitation link</b> from recruiter<br>
                        <span class="small">Invitation link can be found in <br><b>MINE → GET LINKS AND EARN
                                MORE</b></span><br>
                        <img src="@/assets/images/invitation-link.png" class="img-fluid mt-3  w-50">
                    </li>
                    <li class="mb-2">Open the <b>link</b></li>
                    <li class="mb-2"><b>Fill out the form</b><br>
                        <img src="@/assets/images/register.png" class="img-fluid mt-3  w-50">
                    </li>
                    <li class="mb-2">Accept <b>privacy policy</b></li>
                    <li class="mb-2">Click <b>Register</b></li>
                </ol>
                
                <div>
                    <strong class="text-danger">Note:</strong>
                    <ol>
                        <li>After registration, you may download the application from the website, and proceed to recharging</li>
                    </ol>
                </div>

            </div>


            <!-- STEP 4 -->
            <div v-if="currentSection === 'recharge'">

                <h5>Recharging Your Account</h5>

                <ol>
                    <li class="mb-2">Go to <b>ASSETS</b></li>
                    <li class="mb-2">Click <b>Recharge</b></li>
                    <li class="mb-2">Enter or Select <b>deposit amount</b><br> and <b>Select USDC(ERC20)</b><br>
                        <img src="@/assets/images/recharge-form.png" class="img-fluid mt-3  w-50">
                    </li>
                    <li class="mb-2">Click <b>NEXT</b></li>
                    <li class="mb-2">Copy <b>recharge address</b><br>
                        <img src="@/assets/images/recharge-address.png" class="img-fluid mt-3  w-50">
                    </li>
                    <li class="mb-2"><b>Switch</b> to the <b>Coins.ph</b> app</li>
                    <li class="mb-2">From <b>Homepage</b>, go to <b>Portfolio</b></li>
                    <li class="mb-2">Select <b>USDC</b></li>
                    <li class="mb-2">Click <b>Withdraw</b></li>
                    <li class="mb-2">Select <b>External Wallet</b></li>
                    <li class="mb-2">Fill up the <b>Send Crypto</b> form<br>
                        <img src="@/assets/images/send-crypto.png" class="img-fluid mt-3  w-50">
                    </li>
                    <li class="mb-2"><b>Submit the form</b> once filled up</li>
                    <li class="mb-2">On the next page, select <b>Myself</b></li>
                    <li class="mb-2">Tick the checkbox <b>"whitelist"</b></li>
                    <li class="mb-2">Fill up the fields with <b>"Others"</b> as value</li>
                    <li class="mb-2"><b>Confirm</b> and <b>Verify</b> the transaction via <b>Facial Recognition or SMS and EMAIL
                            Verification</b></li>
                </ol>

                
                <div>
                    <strong class="text-danger">Note:</strong>
                    <ol>
                        <li>Once the <b>verification is completed</b>, a <b>Transferring receipt</b> will be displayed. Kindly <b>wait in the Acccat application</b> to receive the funds.</li>
                        <li>Once the funds are <b>received</b>, you may now <b class="text-success">start mining for USDC</b>.</li>
                    </ol>
                </div>

            </div>

        </div>

        

        <div class="d-flex justify-content-between align-items-center p-3">

            <button class="btn btn-outline-secondary btn-sm" @click="prevSection"
                :disabled="currentSection === sections[0]">
                ← Previous
            </button>

            <strong>
                Step {{ sectionIndex + 1 }} / {{ sections.length }}
            </strong>

            <button class="btn btn-outline-primary btn-sm" @click="nextSection"
                :disabled="currentSection === sections[sections.length - 1]">
                Next →
            </button>

        </div>

    </div>

</template>



<script>
export default {

    data() {
        return {

            currentSection: 'requirements',

            sections: [
                'requirements',
                'coins',
                'usdc',
                'acccat',
                'recharge'
            ]

        }
    },

    computed: {

        sectionIndex() {
            return this.sections.indexOf(this.currentSection)
        }

    },

    methods: {

        nextSection() {

            if (this.sectionIndex < this.sections.length - 1) {
                this.currentSection = this.sections[this.sectionIndex + 1]
                window.scrollTo(0, 0)
            }

        },

        prevSection() {

            if (this.sectionIndex > 0) {
                this.currentSection = this.sections[this.sectionIndex - 1]
                window.scrollTo(0, 0)
            }

        },

        logout() {
            localStorage.removeItem('access')
            this.$router.push('/')
        }

    }

}
</script>
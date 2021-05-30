<template>
<div>
    <div class="card card-body mb-2">
        <strong>Signature Preview</strong>
        <hr>
        <table style='width: 760px; height: auto; font-family: sans-serif; background: url(https://i.postimg.cc/T114xfKp/bg-gradiant.png); background-repeat: no-repeat; padding: 10px; background-size: cover; color: #fff; border-radius: 10px; margin: 0;'>
            <tbody>
            <tr>
                <td>
                <img style='width: 180px; height: auto; padding: -10px;' src='https://adondevelopment.com/clients/2021_sig_directory/images/AOG-logo_white.png' alt='AdOn logo'>
                </td>
                <td style='padding-top: 10px;'>
                    <strong style='font-size: 16px;'>
                        {{ sigdata.name }}<br>
                        <small>{{ sigdata.position }}</small>
                    </strong>
                    <p style='font-size: 12px;'>
                        <a v-if="sigdata.phoneOnly" href='`tel:${sigdata.phoneNumber}`' target='_blank' style='text-decoration: none; color: #fff; align-items: center;'>
                            <span>
                                <img style='width: 12px; align-items: center;' src='https://adondevelopment.com/clients/2021_sig_directory/images/icon-01.png' alt='phone'>
                            </span> {{ sigdata.phoneNumber }}
                        </a>
                        <br v-if="sigdata.phoneOnly">
                        <a v-if="sigdata.mobileOnly" href='tel:' target='_blank' style='text-decoration: none; color: #fff; align-items: center;'>
                            <span>
                                <img style='width: 12px; align-items: center;' src='https://adondevelopment.com/clients/2021_sig_directory/images/icon-mobile-01.png' alt='mobile'>
                            </span> {{ sigdata.mobileNumber }}
                        </a>
                        <br v-if="sigdata.mobileOnly">
                        <a href='https://www.adongroup.com.au' target='_blank' style='text-decoration: none; color: #fff; align-items: center;'>
                            <span>
                                <img style='width: 12px; align-items: center;' src='https://adondevelopment.com/clients/2021_sig_directory/images/icon-02.png' alt='internet'>
                            </span> www.adongroup.com.au
                        </a>
                    </p>
                </td>
                <td>
                <img style='width: 300px; height: auto; float: right;' src='https://adondevelopment.com/clients/2021_sig_directory/images/AdOn-logo-and-partners-higher-res-updated-v2.gif' alt='Partner'>
                </td>
            </tr>
            <tr>
                <td colspan='3'>
                <p style='line-height: 1.2; font-size: 8px; padding-left: 15px; padding-right: 15px;'>
                    This email, its contents and any attachments are strictly confidential. They must not be used, distributed, copied or read by any person other than the addressee. Unauthorised use, disclosure, copying or reliance on the contents of and attachments to this email by anyone other than the addressee may be unlawful. If you have received this email and attachments in error please contact us at Ad on Group immediately to facilitate its return.
                </p>
                </td>
            </tr>
            </tbody>
        </table>
    </div>
    <div class="card card-body">
        <strong>Generated Signature</strong>
        <hr>
        <table class="table table.hover">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>
                        Position
                    </th>
                    <th v-if="sigdata.phoneOnly">
                        Phone Number
                    </th>
                    <th v-if="sigdata.mobileOnly">
                        Mobile Number
                    </th>
                    <th>
                        View Signature
                    </th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>{{ sigdata.name }}</td>
                    <td>
                        {{ sigdata.position }}
                    </td>
                    <td v-if="sigdata.phoneOnly">{{ sigdata.phoneNumber }}</td>
                    <td v-if="sigdata.mobileOnly">{{ sigdata.mobileNumber }}</td>
                    <td>
                        <router-link target="_blank" :to="{name: 'signatureView', params: { name:sigdata.name, position:sigdata.position, phoneNumber:sigdata.phoneNumber, mobileNumber:sigdata.mobileNumber, phoneOnly:sigdata.phoneOnly, mobileOnly:sigdata.mobileOnly }}">
                            <p v-if="sigdata.isShow">View</p>
                        </router-link>
                    </td>
                    
                </tr>
            </tbody>
        </table>
    </div>
</div>
    
</template>
<script>
export default {
    props: [
        'sigdata'
    ]
}
</script>
<style scoped>

</style>
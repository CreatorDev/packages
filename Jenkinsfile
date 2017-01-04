#!/usr/bin/env groovy

properties([
    parameters([
        string(defaultValue: 'ci40', description: 'OpenWrt branch to test against', \
            name: "OPENWRT_BRANCH")
    ])
])

stage('Trigger openwrt build') {
    build job: "../openwrt/${params.OPENWRT_BRANCH}", parameters: [
        string(name: 'OVERRIDE_PACKAGES', value: "${BRANCH_NAME}")
    ]
}

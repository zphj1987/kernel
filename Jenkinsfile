/**
properties([
  parameters([
    string(defaultValue: '100', description: 'RELEASE number', name: 'RELEASE_NUMBER'),
    string(defaultValue: 'stable-4.4-rockpis', description: 'RELEASE number', name: 'RELEASE_REPO_BRANCH'),
    string(defaultValue: 'rk3308_linux_defconfig', description: 'kernel defconfig', name: 'KERNEL_DEFCONFIG'),
    string(defaultValue: 'radxa', description: 'GitHub username or organization', name: 'GITHUB_USER'),
    string(defaultValue: 'kernel', description: 'GitHub repository', name: 'GITHUB_REPO'),
  ])
])
*/

node {
  timestamps {
    wrap([$class: 'AnsiColorBuildWrapper', colorMapName: 'xterm']) {
      stage "Environment"
      checkout scm

      def environment = docker.build('build-environment:build-kernel', 'docker')

      environment.inside("--privileged -u 0:0") {
        withEnv([
          "USE_CCACHE=true",
          "KERNEL_DEFCONFIG=$KERNEL_DEFCONFIG",
          "RELEASE_NUMBER=$BUILD_NUMBER",
          "RELEASE_REPO_BRANCH=$RELEASE_REPO_BRANCH",
          "GITHUB_USER=$GITHUB_USER",
          "GITHUB_REPO=$GITHUB_REPO",
        ]) {
            stage ('Environment') {
              sh '''#!/bin/bash
                set -xe

                tar xvf ./gcc-linaro-7.3.1-2018.05-x86_64_aarch64-linux-gnu.tar -C /usr/local/
              '''
              }

            stage ('Package') {
              sh '''#!/bin/bash
                set -xe

                make distclean
                ./dev-make kernel-package
                ./dev-make rockpis-dtbo-package
              '''
            }

            stage ('Release') {
              sh '''#!/bin/bash
                set -xe
                shopt -s nullglob

                export RELEASE_NAME="$(./dev-make version)"
                export RELEASE_TITLE="$(./dev-make version)"
                export DESCRIPTION=" "

                github-release release \
                  --target ${RELEASE_REPO_BRANCH} \
                  --tag "${RELEASE_NAME}" \
                  --name "${RELEASE_TITLE}" \
                  --description "${DESCRIPTION}" \
                  --draft

                for file in ../*$(./dev-make info)*.deb; do
                  github-release upload \
                    --tag "${RELEASE_NAME}" \
                    --name "$(basename "$file")" \
                    --file "$file"
                done

                github-release upload \
                  --tag "${RELEASE_NAME}" \
                  --name "rockpis-dtbo.tar.gz" \
                  --file "../rockpis-dtbo.tar.gz"

                github-release edit \
                  --tag "${RELEASE_NAME}" \
                  --name "${RELEASE_TITLE}" \
                  --description "${DESCRIPTION}"

                rm ../*$(./dev-make info)*.deb
                rm ../rockpis-dtbo.tar.gz
              '''
            }
        }
      }
    }
  }
}

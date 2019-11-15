pipeline {
    agent { label "slave" }
    environment{
        dockerVersion="Kul-test"
    }
    stages {
        stage('Test trigger to deploy job') {
            when {
                anyOf {
                    branch 'develop';
                    branch 'master'
                }
            }
            steps {
                build job: 'kul-deploy', parameters: [string(name: 'dockerVersion', value: env.dockerVersion)]
            }
        }
    }
}

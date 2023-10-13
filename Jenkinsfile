pipeline {
    agent any
    stages {
        stage('version-control') {
            steps {
                checkout ([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'etechapp-id', url: 'https://github.com/Team7-Etechapp/project9-group-repo.git']]])
            }
        }
        stage ('parallel-job') {
            parallel {
                stage('system-statisctics') {
                    steps {
                        sh 'bash -x /var/lib/jenkins/workspace/etechapp-project-pipelinejob/systemstatus.sh'
                    }
                }
                stage('build') {
                    steps {
                        sh 'ls -lh
                    }
                }
            }
        }
        stage('security-check') {
            steps {
                sh 'bash -x /var/lib/jenkins/workspace/etechapp-project-pipelinejob/jenkinsstatus.sh'
                sh 'pwd'
            }
        }
        stage('parallel-job-2') {
            parallel {
                stage('test') {
                    steps {
                        echo 'Testing to be initiated'
                    }
                }
                stage('deploy') {
                    steps {
                        echo 'Deploying to be initiated'
                    }
                }
            }
        }
        stage('post-build-check') {
            steps {
                echo 'Post build check to be initiated'
            }
        }
        stage('publish') {
            steps {
                echo 'Publishing to be initiated'
            }
        }
        stage('Test'){
            steps{
                echo "Testing"
            }
        }
    }
}

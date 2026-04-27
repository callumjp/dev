// Java-based

pipeline{
    agent {label "jenkinsworker01"}
    options{
        timeout(time: 5, "MINUTES")
        timestamps()
    }
    stages{
        stage("Make a directory""){
            steps{
                sh "mkdir jenkins-test"
            }
        }
        stage("add a file"){
            steps{
                sh "touch jenkins-test/file.txt"
            }
        }
    }
    post {
        always{
            archiveArtifacts artifacts: "jenkins-test/*.txt", allowEmptyArchive: true
        }
    }
}
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
			    sh 'mvn clean install'
                sh 'echo $GIT_COMMIT'
                sh 'echo $GIT_PREVIOUS_SUCCESSFUL_COMMIT'
                sh "git diff --name-only --oneline $GIT_PREVIOUS_SUCCESSFUL_COMMIT $GIT_COMMIT > result2.txt"
                sh '../../../embold_ci_cd_wrapper-1.0-SNAPSHOT/bin/embold-ci-cd-wrapper -c repository-configuration.json -lf result2.txt'
            }
        }
    }
}

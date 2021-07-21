pipeline {
    
    agent {
        docker {
            image 'ruby'
        }
    }
    
    stages {
        
        stage ('Build'){
            steps {
                 echo 'Building or Resolve Dependences!'
                 sh 'bundle install'
            }
        }
        stage ('Test'){
            steps {
                echo 'Running regression tests'
                sh 'bundle exec cucumber'
            }
        }
        stage ('UAT') {
            steps {
                echo 'Wait for User Acceptance'
                input (message: 'Go to production?', ok: 'Yes')
            }
        }
        stage('Prod') {
            steps {
                echo 'WebApp is Ready =)'
            }
        }
    }
    
}
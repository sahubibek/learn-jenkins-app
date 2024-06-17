pipeline {
    agent any
    parameters {
        booleanParam(name: 'SKIP_BUILD', defaultValue: false, description: 'Skip the build stage')
        booleanParam(name: 'SKIP_TESTS', defaultValue: false, description: 'Skip the test stage')
    }
    stages {
        stage('Build') {
            when {
                expression { !params.SKIP_BUILD }
            }
            steps {
                echo 'Building...'
                // Your build steps here
            }
        }

 stage('Set Script Permissions') {
            steps {
                script {
                    sh 'chmod +x my_script.sh'
                }
            }
        }
        stage('Run Shell Script') {
            steps {
                script {
                    // Assuming 'my_script.sh' is in the root of your repository
                    sh './my_script.sh'
                }
            }
        }
 
        stage('Test') {
            when {
                expression { !params.SKIP_TESTS }
            }
            steps {
                echo 'Testing...'
                // Your test steps here
            }
        }
        // Other stages...
    }
}

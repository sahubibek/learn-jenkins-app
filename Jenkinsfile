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

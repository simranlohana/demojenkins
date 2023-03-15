pipeline {
    agent any
    environment {
        name = 'simran'
    }
    parameters {
        string(name: 'person', defaultValue: 'Simran Lohana', description: 'Who are you?')
        booleanParam(name: 'isFemale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jaipur', 'Mumbai', 'Pune'], description: "")
    }
    stages {
        stage('Test') {
            steps {
                sh '''
					ls
					date 
					pwd
					'''
            }
        }
        stage('Enviroment Variables') {
            steps {
                sh 'echo "${BUILD_NUMBER}"'
                sh 'echo "${name}"'
                sh 'echo "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we Should"
            }
            
            steps{
                echo "deploy on prod"
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
}

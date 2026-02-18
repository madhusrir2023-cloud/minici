pipeline {
    agent any

    triggers {
        pollSCM('H/1 * * * *')
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java file...'
                bat 'javac CI.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java CI'
            }
        }

        stage('Archive') {
            steps {
                echo 'Archiving artifacts...'
                archiveArtifacts artifacts: '*.class'
            }
        }
    }
}

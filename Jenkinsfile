pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                echo "Clone repo."
                git branch: 'main', url: 'https://github.com/HanishaS28/exam_1228.git'
            }
        }
        stage('Compile'){
            steps{
                echo "Compile"
                bat 'javac Factorial.java TestFactorial.java'
            }
        }
        stage('Run'){
            steps{
                echo "Run"
                bat 'java Factorial'
            }
        }
        stage('Package JAR'){
            steps{
                echo "Build"
                bat 'jar cfm factorial.jar manifest.txt Factorial.class'
            }
        }
        stage('Archive JAR'){
            steps{
                echo "Deploy"
                archiveArtifacts artifacts: 'factorial.jar'
            }
        }
    }
    post{
        success{
            echo 'Success'
        }
        failure{
            echo 'Failure'
        }
    }
}

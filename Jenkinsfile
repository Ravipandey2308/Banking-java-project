pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Ravipandey2308/Banking-java-project/'
                 echo 'github url checkout'
            }
        }
        stage('2.code compile with Ravi'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('3.code testing with Ravi'){
            steps{
                sh 'mvn test'
            }
        }
        stage('4.qa with Ravi'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('5.package with Ravi'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile') {
          steps {
            script {
                    sh 'docker build -t myimg .'
                   }
                }
        }

        // stage('run dockerfile'){
        //   steps{
        //        sh 'docker build -t myimg .'
        //    }
        //  }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}

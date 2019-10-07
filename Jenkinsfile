pipeline {
    agent { docker { image 'maven:3.6.0' } }
    stages {
        stage('build') {
            steps {
                    sh 'test -d ./demo-open-legacy && rm -r ./demo-open-legacy'
                    sh 'git clone https://github.com/yuvalzaidel/demo-open-legacy.git'
                    sh 'cd demo-open-legacy/ && mvn clean install' 
                    sh 'cd demo-open-legacy/ && mvn clean package > ./target/demo-0.0.1-SNAPSHOT.jar'
    
            }
        }
    }
}
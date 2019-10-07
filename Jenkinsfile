pipeline {
    agent any
    stages {
        stage('build') {
            steps {

                    sh 'git clone https://github.com/yuvalzaidel/demo-open-legacy.git'
                    sh 'cd demo-open-legacy/ && mvn clean install' 
                    sh 'cd demo-open-legacy/ && mvn clean package > ./target/demo-0.0.1-SNAPSHOT.jar'
                    sh 'docker build -t demo -f demo-open-legacy/Dockerfile .'
            }
        }
    }
}

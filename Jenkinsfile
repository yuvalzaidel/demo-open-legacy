pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                    sh 'test -d ./demo-open-legacy && rm -r ./demo-open-legacy'
                    sh 'git clone https://github.com/yuvalzaidel/demo-open-legacy.git'
                    sh 'cd demo-open-legacy/ && mvn clean install' 
                    sh 'cd demo-open-legacy/ && mvn clean package > ./target/demo-0.0.1-SNAPSHOT.jar'
                    sh 'cd demo-open-legacy/ && docker build -t demo -f Dockerfile .'
                    sh 'cd demo-open-legacy/ && docker run -d -p 3333:8080 demo'
            }
        }
    }
}

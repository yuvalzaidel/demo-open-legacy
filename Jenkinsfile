pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                    sh 'test -d ./demo-open-legacy && rm -r ./demo-open-legacy'
                    sh 'git clone https://github.com/yuvalzaidel/demo-open-legacy.git'
                    sh 'cd demo-open-legacy/ && mvn clean install' 

                    sh 'docker build -t demo -f demo-open-legacy/Dockerfile .'
            }
        }
    }
}

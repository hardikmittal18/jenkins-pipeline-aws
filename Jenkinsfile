pipeline{
    agent any
    stages {
        stage('Build')
        {
            steps {
                sh 'echo "Hello World"'
                sh '''
                echo "multiline steps shell "
                ls -lah
                '''
            }
        }
    }
}

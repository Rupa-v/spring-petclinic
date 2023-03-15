pipeline { 
    agent { label 'JDK_MAVEN' }
     stages {
        stage ('vcs') {  
            steps {
                git url: 'https://github.com/Rupa-v/spring-petclinic.git',
                branch: 'dev'
            }   
        }
        stage ('package') {
            steps {
                sh """
                      export PATH=/usr/lib/jvm/java-1.17.0-openjdk-amd64/bin:$PATH
                      mvn package
                   """
            }
        }
    }
}


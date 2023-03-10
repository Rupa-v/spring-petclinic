pipeline { 
    agent { label 'JDK_MAVEN' }
     stages {
        stage ('vcs') {  
            steps {
                git url: 'https://github.com/Rupa-v/spring-petclinic.git',
                branch: 'main'
            } 
        }        
        stage ('package') {
            steps {
                sh 'export PATH=/usr/lib/jvm/java-1.17.0-openjdk-amd64/bin:$PATH'
                sh 'mvn package'
            }
        }
        stage('SonarQube analysis') {
            steps{
                withSonarQubeEnv('SONAR_QUBE') {
                    sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=springorg_spc1 -Dsonar.organization=springorg'
            
                }            
            }
        }  
    }
}



node {
    stage('SCM') {
        checkout scm
    }
  stage('SonarQube Analysis') {
    def mvn = tool 'Maven392';
    withSonarQubeEnv('My local sonar') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -DskipTests -Dsonar.token=sqa_6f469923849560c5efa555e9e3bc8f86ff824b3d -Dsonar.projectKey=JavaTest"
    }
  }
}

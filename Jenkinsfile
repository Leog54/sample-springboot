node {
    stage("Checkout Source Code"){
        echo "Checkout Source Code"
        checkout scm
    }

    stage ("Run init tests") {
        echo "Running unit tests"
        sh "mvn test"
    }

    stage ("Build project") {
        echo "Build project"
        sh "mvn package -DskipTests"
    }

    configFileProvider([configFile(fileId: '212072eb-00f1-4141-849a-8e7085f86f83', variable: 'MAVEN_SETTINGS')]) {
    // Exécuter la commande mvn avec le settings
    mvn deploy -s $MAVEN_SETTINGS -Preposilite
}
}
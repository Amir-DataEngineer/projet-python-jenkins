pipeline {
    agent any

    stages {
        stage('Installer les dépendances') {
            steps {
                echo 'Installation des dépendances...'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Exécuter le script Python') {
            steps {
                echo 'Exécution du script scraper.py...'
                sh 'python scraper.py'
            }
        }

        stage('Archiver le fichier CSV') {
            steps {
                echo 'Archivage du fichier data.csv...'
                archiveArtifacts artifacts: 'data.csv', fingerprint: true
            }
        }
    }
}

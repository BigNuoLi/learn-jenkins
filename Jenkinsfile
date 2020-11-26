pipeline {
    agent any
    stages {
        stage('Start Stage') {
            steps {
                echo 'This stage will be executed first.'
            }
        }
        stage('Parallel Stage') {
            failFast true
            parallel {
                stage('P1') {
                    steps {
                        echo 'Parallel Exec 1'
                    }
                }
                stage('P2') {
                    steps {
                        echo 'Parallel Exec 2'
                    }
                }
                stage('P3') {
                    stages {
                        stage('Nested 1') {
                            steps {
                                echo 'In stage Nested 1 within Branch C'
                            }
                        }
                        stage('Nested 2') {
                            steps {
                                echo 'In stage Nested 2 within Branch C'
                            }
                        }
                    }
                }
            }
        }
        stage('End Stage') {
            steps {
                echo 'This stage willl be executed after parallel.'
            }
        }
    }
}

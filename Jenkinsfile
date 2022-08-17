def gv
CODE_CHACHES = getGitChanges()
pipeline {
    agent any

    enviornment {
        NEW_VIRSION = '1.6.5'
        NEW_CREDINTAILS = credentails('	server-credintails')

    }

    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }

                echo "my version is ${NEW_VIRSION}"
            }
        }
        stage("build jar") {

            when{
                expression{
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'master'

                }
            }
            steps {
                script {
                    echo "building jar"
                    //gv.buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //gv.buildImage()
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}
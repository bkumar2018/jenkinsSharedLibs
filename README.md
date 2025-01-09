# jenkinsSharedLibs

This is for writing resuable jenkins pipeline code, jenkins shared library and advanced jenkins pipeline 

Refer link : https://www.jenkins.io/doc/book/pipeline/shared-libraries/

Login to jenkins using id/pwd:
Got to:
Manage Jenkins -> Configure System->  at Section: Global Pipeline Libraries
And add the Name and Git repo details like url and branch name
name: 'demo-shared-libs' and save it.

Now create a jenkin job with pipeline and configure pipeline code as below:
..............................................................................

@Library('demo-shared-libs') _

pipeline{
    agent any
    stages{
        stage('Demo'){
            steps{
                welcome("Birender Kumar")
                welcome("Chanchal Singh")
                
                script{
                    calculator.add(25,65)
                    calculator.mul(5,6)
                }
            }
        }
    }
}
..............................................................................


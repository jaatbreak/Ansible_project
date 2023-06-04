pipeline{
    agent{
        label "test"
    }
    stages{
        stage("Pulling the code from scm"){
           steps{
               git 'https://github.com/jaatbreak/Ansible_project.git'
           }
        }
        stage("Running The yaml file to ansible server "){
            steps{
                sh 'ansible-playbook webserver.yaml'
            }
        }
        stage("The website running on the ansible node"){
            steps{
                sh 'echo "The website is ruunig perfect "'
            }
        }
    }
}

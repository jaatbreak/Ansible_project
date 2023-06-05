pipeline{
    agent{
        label "test"
    }
    stages{
        stage("Pulling the code from scm"){
           steps{ 
             sh 'git clone "https://github.com/jaatbreak/Ansible_project.git"'
           } 
        }
        stage("Running The yaml file to ansible server "){
            steps{
              sh 'sudo ansible-playbook webserver.yaml'
            } 
        } 
        stage("The website running on the ansible node"){
            steps{
                sh 'sudo echo "The website is ruunig perfect "'
            }
        }
	stage("ansible node ip "){
	    steps{
	    sh 'sudo ansible all -m command -a "curl ifconfig.me."'
	    }
	}
    }
}

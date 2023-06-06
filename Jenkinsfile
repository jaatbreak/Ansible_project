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
	stage("Checking The Ansible Node Health"){
	steps{
		script{
	      Boolean userInput = input(id: 'Proceed1', message: 'Do You want Ansible Node IP?', parameters: [[$class: 'BooleanParameterDefinition', defaultValue: true, description: '', name: 'Please confirm you agree with this']])
                				echo 'userInput: ' + userInput
	      }
	   }
	}
    }
}

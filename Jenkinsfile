pipeline{
	agent { node { label 'msbuild' } }
	stages{
		stage('Code-Check'){
			steps{
				echo "Example stage"
			}
		}
    		stage('Build'){
			steps{
				bat 'build_debug.cmd'
			}
		}
	}
	post{
		always{
			archive '*/target/**/*'
			junit '*/target/reports/*.xml'
		}
		failure{
			echo "yikes, build broke"
		}
	}
}

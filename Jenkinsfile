pipeline{
	agent {'msbuild'}
	stages{
		stage('Code-Check'){
			echo "Example stage"
		}
    stage('Build'){
			bat 'build_debug.cmd'
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

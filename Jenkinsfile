pipeline {
    agent any
    
    parameters {
        string(name: 'NUM_1', defaultValue: '', description: 'Enter the first number')
        string(name: 'NUM_2', defaultValue: '', description: 'Enter the second number')
        choice(name: 'OPERATION', choices: ['+', '-', '*', '/'], description: 'Choose an operation to perform')
    }

    environment {
        RESULT = ''
    }

    stages {
        stage('CALCULATOR') {
            steps {
                sh '''
                    NUM1=${NUM_1}
                    NUM2=${NUM_2}
                    OP="${OPERATION}"

                    echo "Calculating: $NUM1 $OP $NUM2"

                    case "$OP" in
                    "+")
                        RESULT=$((NUM1 + NUM2))
                        ;;
                    "-")
                        RESULT=$((NUM1 - NUM2))
                        ;;
                    "*")
                        RESULT=$((NUM1 * NUM2))
                        ;;
                    "/")
                        if [ "$NUM2" -eq 0 ]; then
                            echo "Error: Division by zero is not possible"
                            exit 1

                        fi
                        RESULT=$((NUM1 / NUM2))
                        ;;
                    *)
                        echo "INVALID OPERATION: $OP"
                        exit 1
                        ;;

                    esac

                    echo "Result: $NUM1 $OP $NUM2 = $RESULT"
                '''
            }
        }
    }
}







.circleci/config.yml
# Use the latest 2.1 version of CircleCI pipeline process engine.
# See: https://circleci.com/docs/configuration-reference
version: 2.1

# Define a job to be invoked later in a workflow.
# See: https://circleci.com/docs/configuration-reference/#jobs
jobs:
  say-hello:
    # Specify the execution environment. You can specify an image from Docker Hub or use one of our convenience images from CircleCI's Developer Hub.
    # See: https://circleci.com/docs/configuration-reference/#executor-job
    docker:
      - image: cimg/base:stable
    # Add steps to the job
    # See: https://circleci.com/docs/configuration-reference/#steps
    steps:
      - checkout
      - run:
          name: "Say hello"
          command: "echo Hello, World!"

# Orchestrate jobs using workflows
# See: https://circleci.com/docs/configuration-reference/#workflows
workflows:
  say-hello-workflow:
    jobs:
      - say-hello

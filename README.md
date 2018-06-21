# cfn-modules: AWS Lambda evrnt source: cron

Cron event source for AWS Lambda function with [alerting](https://www.npmjs.com/package/@cfn-modules/alerting).

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/lambda-event-source-cron
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  Function:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        LambdaModule: !GetAtt 'Lambda.Outputs.StackName' # required
        AlertingModule: !GetAtt 'Alerting.Outputs.StackName' # optional
        ScheduleExpression: 'rate(1 day)' # optional
      TemplateURL: './node_modules/@cfn-modules/lambda-function/module.yml'
```

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>LambdaModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/lambda-function">lambda-function module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>AlertingModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alerting">alerting module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ScheduleExpression</td>
      <td>The schedule or rate (frequency) that determines when CloudWatch Events runs the rule (for valid values, see )</td>
      <td>rate(1 day)</td>
      <td>no</td>
      <td><a href="http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html">valid values</a></td>
    </tr>
  </tbody>
</table>

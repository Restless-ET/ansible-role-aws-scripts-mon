Restless-ET.aws-scripts-mon
=========

An Ansible role for installing and configuring the Amazon CloudWatch Monitoring Scripts for Amazon Elastic Compute Cloud (Amazon EC2).

Followed instructions from [Monitoring Memory and Disk Metrics for Amazon EC2 Linux Instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/mon-scripts.html).

Requirements
------------

Nothing worth mentioning ...

Role Variables
--------------

- `aws_scripts_mon_version` - The version of monitoring scripts to install. Defaults to: `1.2.1`
- `aws_scripts_mon_base_directory` - The base directory where the scripts will be installed. Defaults to: `/opt`
- `aws_scripts_mon_cron_user` - The user for which the scripts will run as. Defaults to: `{{ ansible_user }}`
- `aws_scripts_mon_options` - The monitoring script options (`--from-cron` is always assumed). Defaults to: `"--disk-space-util --disk-path=/"`.
- `aws_scripts_mon_access_key` - Your AWS Access Key. You need to define this (if not using IAM) or the role will fail to execute.
- `aws_scripts_mon_secret_key` - Your AWS Secret Key. You need to define this (if not using IAM) or the role will fail to execute.
- `aws_scripts_mon_use_iam` - If you want to authenticate with AWS IAM role permissions instead of access keys set this to `true`, this way the keys will not be considered as required. Defaults to: `false`.


Dependencies
------------

No dependecies. :-)

Example Playbook
----------------

Add `Restless-ET.aws-scripts-mon` to your roles in your playbook. E.g.:

    - hosts: aws_ec2_instances
      roles:
         - { role: Restless-ET.aws-scripts-mon,
             aws_scripts_mon_access_key: YourAccessKeyID,
             aws_scripts_mon_secret_key: YourSecretAccessKey
           }

License
-------

MIT

Author Information
------------------

Artur Melo

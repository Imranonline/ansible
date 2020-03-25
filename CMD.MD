ansible -i hosts 3.95.168.159 -m ping

ansible -i hosts -m ping


ssh -i "mykey.pem" ec2-user@ec2-3-95-168-159.compute-1.amazonaws.com

ansible -i hosts ec2-3-95-168-159.compute-1.amazonaws.com -u ec2-user --private-key mykey.pem -m ping

ansible -i hosts 18.220.59.96 -m ping -u root --ask-pass

ansible -i hosts -m ping -u root --ask-pass


ansible -i hosts my_grp -m ping -u root --ask-pass

ssh -i "mykey.pem" ec2-user@ec2-3-89-98-237.compute-1.amazonaws.com

ansible -i hosts ec2-18-220-59-96.us-east-2.compute.amazonaws.com -u ec2-user --private-key mykey.pem -m ping


ansible -i hosts 18.220.59.96 -m ping


ssh -i "mykey.pem" ec2-user@ec2-18-220-59-96.us-east-2.compute.amazonaws.com

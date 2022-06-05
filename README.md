### Instruction on how to build VPC 

### Please copy paste below code 
```
module "vpc-t1" {
    source  = "rus777777/vpc-t1/aws"
    
    region             = "us-east-1"
    cidr_block         = "10.0.0.0/16"
    public_subnet1     = "10.0.1.0/24"
    public_subnet2     = "10.0.2.0/24"
    public_subnet3     = "10.0.3.0/24"
    private_subnet1    = "10.0.101.0/24"
    private_subnet2    = "10.0.102.0/24"
    private_subnet3    = "10.0.103.0/24"
    enable_nat_gateway = true
    
    tags = {
        Name = "main"
    }
}
```
### To get the output, please add the following code 
```
output "vpc_id" {
  value = aws_vpc.main.id
}
output "public_subnet1" {
  value = aws_subnet.public1.id
}
output "public_subnet2" {
  value = aws_subnet.public2.id
}
output "public_subnet3" {
  value = aws_subnet.public3.id
}
output "private_subnet1" {
  value = aws_subnet.private1.id
}
output "private_subnet2" {
  value = aws_subnet.private2.id
}
output "private_subnet3" {
  value = aws_subnet.private3.id
}

```
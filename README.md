resource "aws_instance" "web" {
  ami                         = var.ami_id
  instance_type               = var.ec2_size
  availability_zone           = var.availability_zone
  associate_public_ip_address = true
  vpc_security_group_ids      = [aws_security_group.wales_sg1.id]
  #}
  tags = {
    Name = var.ec2_tag
  }
}
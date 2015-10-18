FROM centos:7.1.1503
MAINTAINER Craig Struble <strubleca@yahoo.com>

#------------------------------------------------------------------------------
# Update yummy bits and add in some sticky bits (tar)
#------------------------------------------------------------------------------
RUN yum -y update && yum -y upgrade
RUN yum install -y tar
RUN yum groupinstall -y 'Development Tools'

#------------------------------------------------------------------------------
# Install Perl with CPAN to use CPAN builds
#------------------------------------------------------------------------------
RUN yum install -y cpanminus
RUN yum install -y perl-ExtUtils-Embed

#------------------------------------------------------------------------------
# Now install the packages we want with CPAN instead of yum
#------------------------------------------------------------------------------
RUN cpanm PAR::Packer

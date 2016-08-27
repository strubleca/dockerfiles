FROM r-flexdashboard
MAINTAINER Craig Struble <strubleca@yahoo.com>

#------------------------------------------------------------------------------
# Prepare the root directory for managing files.
#------------------------------------------------------------------------------
ENV FD_ROOT /fd
ENV FD_BUILD $FD_ROOT/build
ENV FD_HTML /var/www/html
RUN mkdir $FD_ROOT $FD_BUILD 

#------------------------------------------------------------------------------
# Copy markdown sources for dashboards and render them.
#------------------------------------------------------------------------------
WORKDIR $FD_BUILD
COPY sample1.Rmd .
RUN Rscript -e 'rmarkdown::render("sample1.Rmd")'

#------------------------------------------------------------------------------
# Place the resulting html files into the HTML directory
#------------------------------------------------------------------------------
RUN cp *.html $FD_HTML

#------------------------------------------------------------------------------
# Clean up the build directory
#------------------------------------------------------------------------------
RUN rm -f *

#------------------------------------------------------------------------------
# Setup nginx to serve up the HTML directory
#------------------------------------------------------------------------------

# Nothing to do.

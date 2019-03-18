FROM: simexp/minc-toolkit:1.9.15

RUN LD_LIBRARY_PATH="" && add-apt-repository ppa:octave/stable octave -y 
RUN LD_LIBRARY_PATH="" && apt-get update -y 
RUN LD_LIBRARY_PATH="" && apt-get install octave -y


RUN octave --eval "pkg load all"

RUN echo 'cellfun (@(x) pkg ("load", x.name), pkg ("list"));' >> /etc/octave.conf
RUN echo more off >> /etc/octave.conf
RUN echo save_default_options\(\'-7\'\)\; >> /etc/octave.conf
RUN echo graphics_toolkit gnuplot >> /etc/octave.conf
ENV OCTAVE_VERSION_INITFILE /etc/octave.conf

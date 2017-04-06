# rpi3_transmitter
a compiled version of raspberry pi fm transmitter with the removal of frequencies limit (you can now use frequency under 88hz &amp; above 108hz

#How to use :
#wav file
sudo ./chetouane -f frequency -s source.file

example:
sudo ./chetouane -f 89.9 -s recording.wav


#USB-Sound Card

To use a USB sound-card type this:

arecord -D hw:1,0 -c1 -d 0 -r 22050 -f S16_LE | sudo ./chetouane -f 89.9 -

Some devices have problems with this command (there is a warning in the terminal like buffer overflow and after a few seconds - the transmitting gets slow and will stop), then you can use the following:

arecord -D plughw:1,0 -c1 -d 0 -r 22050 -f S16_LE | sudo ./chetouane -f 89.9 -


#Law

Please keep in mind that transmitting on certain frequencies without special permissions may be illegal in your country.

#New features

    works on RPi 1, 2 and 3
    reads mono and stereo files
    reads data from stdin
    based on threads

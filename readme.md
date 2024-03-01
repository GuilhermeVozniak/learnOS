
# Configuracao do ambiente
## instalar o nasm
`sudo apt-get install nasm`
## instalar o xxd
`sudo apt-get install xxd`
## instalar o qemu, usaremos um i-386 16bits
`sudo apt-get install qemu-system-x86` 

# criando o arquivo de boot
## como o arquivo de boot criado se faz preciso compilar para binario, 
## fazemos isso usando o nasm
`nasm <file_name.asm> -f bin -o <output_filename.bin>`
## criando imagem de disket para bootar apartir delar
` cp <output_file_name.bin> lost.img`
## criando uma imagem com 1440k === disket
`truncate -s 1440k lost.img`
## dar boot com o disket criado
`qemu-system-i386 -drive file=lost.img,format=raw,index=0,if=floppy`


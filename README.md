# srpn

I've been playing around for an RPN calculator for strings, because,
why not.

## Input

Enter a value onto the stack by starting it with a `=`. Leading and
trailing whitespace is trimmed and there is no feedback:

	$ ./srpn
	=hello

To see the stack, use `show`:

	$ ./srpn
	=hello
	show
	  # 0: hello

To output the top value, use `output`:

	$ ./srpn
	=hello
	output
	hello

The input strips off trailing whitespace, but you can input a code number
and turn that into a character with `chr`. In the output, the space
character is shown as ␠ (U+2420 sʏᴍʙᴏʟ ꜰᴏʀ sᴘᴀᴄᴇ):

	$ ./srpn
	=world
	=hello
	=32
	chr
	show
	  # 0: ␠
	  # 1: hello
	  # 2: world

The `join` combines the values in slots 1 and 2 with the value in slot 0:

	join
	output
	hello world

You can do this on the command line where each shell word is a line of input:

	$ ./srpn =world =hello =32 chr join output
	hello world

For the rest of it, you'll have to look inside for now.

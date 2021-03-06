# setclip
Maintain and Manage ISPF Clipboards

SETCLIP is an ISPF dialog that makes it easy for a user to create from
one to ten (the ISPF max) ISPF Edit Clipboards from existing datasets
for use during the ISPF session.

The dialog has two modes that are determined by how the command is
called.

Mode 1:  Define, or update, user clipboards

This mode is enabled when the SETCLIP command is invoked without any
parameters and will display an ISPF panel on which the user enters:

   - Clipboard Name
   - Dataset Name where the clipboard data resides
   - Optional Starting and/or Ending records to be copied into the
     clipboard

The row option is either B (Browse), E (Edit), or D (Delete).

The Clipboard name is a 1 to 8 character name that must follow the
standard PDS member naming convention.

The Dataset name is the dataset, or dataset member, where the data is
located to be copied into the clipboard.

The starting and ending record numbers are optional. If not specified
then all records are copied into the clipboard.

Usage note:  By using the starting and ending record numbers the user
can have one dataset with data for multiple clipboards in it.

When the clipboards are defined the ENTER key will create, or update,
the active clipboards. PF3 will update and then exit if changes have
been make, while CANCEL will exit without making any updates.

Mode 2: Create clipboards only

This mode is enabled when the SETCLIP command is invoked with any
non-blank parameter and will process the defined clipboard information
to create the clipboards.

This mode is designed to be used out of the ISPF ZSTART process that
runs when ISPF starts so that the clipboards are available for any
ISPF Edit session during the current ISPF session. Use the SET command
within this dialog for a simple way to create or update the ZSTART
variable.

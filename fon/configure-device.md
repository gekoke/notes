# Assign name to device
configure terminal  -- enter config mode
hostname HOSTNAME   -- assign name to device

# Secure user access 
configure terminal  -- ensure you're in config mode
line console 0      -- switch to console 0
password PASSWORD   -- assign password to user
login               -- enable login verification
end                 -- exit config mode

# Secure privileged access
configure terminal  -- ensure you're in config mode
enable secret SUDOP -- assign privileged access password
login               -- enable login verification
end                 -- exit config mode

# Encrypt the plaintext passwords
configure terminal
service password-encryption
show running-config -- check if passwords are encrypted

# Assign banner for legal purposes
configure terminal
banner motd #Authorized access only!#

# Assign IP (only to switch)
configure terminal
interface vlan 1
ip address IPv4 IPv4-SUBNET-MASK
no shutdown
exit
ip default-gateway 192.168.1.1

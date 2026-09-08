Subnetting is nothing but dividing a network into smaller parts/networks for easy accessibility & control over the network, because for big networks the maintenance & security are very difficult

we always divide the networks into subnets by using the bits in the HOST ID part only.

there are 2 types of subnetting in classfull classification
1. fixed length subnet masking (flsm)
2. variable length subnet masking (vlsm)

in flsm, the subnets are of same length and in vlsm the subnets are of different sizes, so the subnet mask changes for different subnets

a subnet mask is nothing but all 1's in the (NETWORK ID part + SUBNET ID part) continued by all 0's in the HOST ID part.

example : 

subnet mask of class c ip 200.1.2.130 is 255.255.255.192 when there are 4 subnets of flsm, and when we bitwise and the subnet mask and ip addr we get the subnet id of the dest ip addr.

in vlsm the subnet mask changes according to the size of the subnet mask

in CIDR the subnetting is similar to this but the only difference is the representation of the CIDR block when subnetting is done on a CIDR block the no of bits in the NETWORK ID part changes W.R.T the no. of bits used for the subnetting of the CIDR block remaining all same concepts as classfull classification

NOTE : the default gateway addr is 0.0.0.0 i.e., when a packet is sent to the network with a dest addr which is not in the whole network then it returns to where is came from for that the default ip is 0.0.0.0
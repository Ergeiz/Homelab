Pour l'installation de proxmox sur mon MS-01 comme hyperviseur principale, je vais me servir de 3 disques NVMe de 4To, avec la configuration suivante

```mermaid

flowchart LR

id1[NVMe0n1]
id2[NVMe1n1]
id3[NVMe2n1]

R[Zfs RAID 1 (mirrored)]
T[Zfs Tank (un seul disque)]

id1 --> R
id2 --> R

id3 --> T

```




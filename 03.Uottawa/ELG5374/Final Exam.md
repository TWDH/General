# Topic4 

## CSMA

* CSMA: carrier sense multiple access 载波监听多路访问
  * 先听别人 carrier sense，如果忙就等
  * 不忙，传送
  * frame transmission > propagation，因为其他站点已经提前知道了
  * utilization：shorter propagation time, longer frame

* nonpresistent CSMA
  * idle, transmit
  * busy, wait time (probability distribution/ retransmission delay)

* 1-persistent protocol
  * avoid idle channel time
  * transmit as soon as channel goes idle

* p-persistent protocol
  * transmit (p), delay one time unit (1-p)

* CSMA/CD
  * idle, transmit
  * busy, listen -> idle -> transmit
  * collision, transmit jamming signal
  * wait random time (back off), try again

![image-20201221231516865](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221231516865.png)

## ARP

* IP -> MAC 
* TTL (time to live)：存活时间

## Implicit Congestion Signaling

* transmission delay increases
* packet may discarded
* source detect congestion -> reduce flow
* end system的责任，不需要network nodes的任何行动
* no logical connections

## Explicit Congestion Signaling

* use as much of available capacity
* react to congestion
* 网络向终端系统发出网络内拥塞加剧的警报，终端系统采取措施减少网络提供的负载

## ATM

* Asynchronous transfer mode
* little overhead for error control

## gateway

* A gateway connect networks with different upper layer protocol
* 网络层以上实现网络互连，仅用于两个高层协议不同的网络互连。

## DNS

* DNS is a protocol that can map a name to an IP address and vice versa

## Data-Link Layer

* LLC
  * Used for the reliable exchange of information across a link
* MAC
  * Used to allow the sharing of medium by multiple computers

BER = bit error rate (chapter 5)

## Nyquist criterion

* C = 2B $\times$ log~2~(M)
  * B: frequency (Bandwidth)
  * M: Number of discrete level / voltage levels

## Shannon Capacity

* C = B $\times$ log~2~(1 + SNR)
* SNR(db) = 10 $\times$ log~10~(SNR)

![image-20201220175141209](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220175141209.png)



## ARQ performance issue

![image-20201220180316174](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220180316174.png)

* maximum possible utilization

![image-20201220200851419](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220200851419.png)

#### Error free sliding window flow control

![image-20201220180411612](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220180411612.png)![image-20201220181042875](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220181042875.png)

![image-20201220200612556](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220200612556.png)

#### stop and wait

![image-20201220180459990](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220180459990.png)

#### selective reject

![image-20201220180524607](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220180524607.png)

#### go back N

![image-20201220180559647](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201220180559647.png)

## Time propagation

$$
propagation \quad Time = \frac{总路程长度}{传输速度}
$$

## Time transmission

$$
tansmission \quad time = \frac{bits}{bps}
$$

## LDPC-low density parity check code

* addition -> module 2 (XOR)
* parity check matrix: **H**, used in decoding
* G: encoding

![image-20201221142558355](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221142558355.png)

![image-20201221142716021](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221142716021.png)

![image-20201221165003154](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221165003154.png)

![image-20201221165621440](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221165621440.png)

![image-20201221165647742](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221165647742.png)

* Tanner Graph
* f：行数
* c：列数

![image-20201221170228310](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221170228310.png)

* received codeword is **11010101**
* c是收到的数字，c1~c8 -> **11010101**

![image-20201221171158298](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221171158298.png)

![image-20201221171455876](https://raw.githubusercontent.com/TWDH/Leetcode-From-Zero/pictures/img/image-20201221171455876.png)

1. 首先转换每个C~1~, ... , C~8~到如下形式
   1.   C~2~ = C~4~ $$\bigotimes$$ C~5~ $$\bigotimes$$ C~8~
   2. 得出 C~2~=0
   3. 以此类推其他的每个c，以及每个f
2. 表(c)：找到影响c的对应f，然后看这些f给出对应c的值(sent)。最后在这三个数中间，多数获胜。

##  CRC

1. Message D = 1010001101 (10bits)
2. Pattern P = 110101 (6bits)

* k=10
* p = n-k+1=6
* n = 6 + k - 1=15
* n - k  =5 (FCS)

# Quiz 1

1. In a data link protocol, **Error control** is achieved by retransmission of damaged frames.
2. The **propagation** time is the time it takes for a bit to traverse the link between source and destination.
3. The time it takes for a station to emit all of the bits of a frame onto the medium is the **Transmission** time.
4. In a **circuit switching** network, a dedicated communications path is established between two stations through the nodes of the network. The telephone network is the most common example.
5. Individual host and LANs are connected to an Integer Service Provider through a **POP**.
6. A **Network Access Point (NAP)** is a physical facility that probides the infrastructure to move data between connected networks. 
7. **Unshielded** twisted pair is subject to external electromagnetic intergerence, including interference from nearby twisted pair and from noise generated in the environment.
8. In **amplitude shift keying**, the two binary values are represented by two different amplitudes of the carrier frequency. Commonly, one of the amplitudes is zero. One binary digit is represented by the presence, at constant.
9. The use of coding allows a reduction, referred to as the **coding**, and defined as the reduction in decibels to achieve a specified BER of error correcting coded system compared to an uncoded system using the same modulation.

# Quiz 2

1. With **sliding-window** flow control the transmission link is streated as a pipeline that maybe filled with frames in transit. 
2. The form of error control based on sliding-window flow control that is commonly used is: **go-back-N ARQ**
3. The simplest criterion in the selection of a route is to choose the **minimum hop route**
4. In the case of **centralized routing** central node typically makes use of information obtained from all nodes.
5. "Because all routes are tired, at least one copy of the packet to arrive at the destination will have used a minimum-hop route" is a property of **flooding**.
6. drawback of adaptive routing: **It may react too quickly, causing congestion producing oscillation, or too slowly, being irrelevant.**
7. The objective of **congestion control** is to maintain the number of packets within the network below the level at which performance falls off dramatically.
8. A **token bucket** fills at a constant rate up to the capacity of the bucket and empties at a rate dictated by the input data stream while the bucket is not empty.
9. The purpose of the **slow start** mechanism is to gradually expand the window until acknowledgments are received.
10. A problem with **non-presistent CSMA** is that capacity is wasted because the medium will generally remain idle following the end of a transmiision even if there are one or more stations waiting to transmit.
11. One of the rules for CSMA/CD states, "after transmitting the jamming signal, wait a random amount of time, then attempt to transmit again". This random amount of time is referred to as the **back off**.

flow control, amplitude modulation, arq, adaptive routing


























## 1. 1） 162.105.80.128

## 2） 256-192-2=62

## 3） 2^16/(256-192)=2^10=1024

## 2.因为三次握手可以保证任何一次握手出现问题，都是可以被发现或补救的，从而避免了资源的浪费。假定A为客户端，B为服务器。若第一次握手A发送SYN(同步序列

## 编号)传输失败，A,B都不会申请资源，连接失败。如果一段时间内发出多个SYN连接请求，那么A只会接受它最后发送的那个SYN的SYN+ACK（确认字符）回应，忽略其

## 他回应全部回应，B中多申请的资源也会释放；若 第二次握手B发送SYN+ACK传输失败，A不会申请资源，B申请了资源，但收不到A的ACK，过一段时间释放资源。如果

## 是收到了多个A的SYN请求，B都会回复SYN+ACK，但A只会承认其中它最早发送的那个SYN的回应，并回复最后一次握手的ACK；若第三次握手ACK传输失败，B没有收到

## ACK，释放资源，对于后序的A的传输数据返回RST(重置连接)。实际上B会因为没有收到A的ACK会多次发送SYN+ACK，次数是可以设置的，如果最后还是没有收到A的

## ACK，则释放资源，对A的数据传输返回RST。

## 两次握手不成立——假设只有两次握手，当A想要建立连接时发送一个SYN，然后等待ACK，结果这个SYN因为网络问题没有及时到达B，所以A在一段时间内没收到ACK后，

## 再发送一个SYN，B也成功收到，然后A也收到ACK，这时A发送的第一个SYN终于到了B，对于B来说这是一个新连接请求，然后B又为这个连接申请资源，返回ACK，然而

## 这个SYN是个无效的请求，A收到这个SYN的ACK后也并不会理会它，而B却不知道，B会一直为这个连接维持着资源，造成资源的浪费。

## 多次握手没必要——三次握手已经能确保建立可靠的连接，多次握手只会使效率降低；且三次握手后，虽然客户端和服务器只能确认之前的通信情况，无法确认之后的情

## 况，但从这个意义上说，多次握手也无法确认之后的情况。可见，三次握手是最优方案。

## 3.恶意软件：计算机病毒、蠕虫、木马、间谍软件、广告软件等

## 防范措施：安装安全防护/杀毒软件，及时打补丁；使用防火墙, 禁止外部计算机通过网络访问本机；不随便下载运行可执行程序；不打开未知的邮件附件；打开U盘前

## 要先查毒；不随便暴露自己的 email、生日、手机等重要信息；不以 Administrator 权限操作计算机等

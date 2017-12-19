## client demo

### publish stream
```
RTMP *rtmp=RTMP_Alloc();
RTMP_Init(rtmp);
RTMP_SetupURL(rtmp,"rtmp://localhost/publishlive/livestream");
RTMP_EnableWrite(rtmp);
RTMP_Connect(rtmp,NULL);
RTMP_ConnectStream(rtmp,0);
while(RTMP_IsConnected(rtmp)){
    RTMPPacket *packet=(RTMPPacket*)malloc(sizeof(RTMPPacket));
    //...
    RTMP_SendPacket(rtmp,packet,0);
}
RTMP_Close(rtmp);          
RTMP_Free(rtmp);
RTMPPacket_Free(packet);

```
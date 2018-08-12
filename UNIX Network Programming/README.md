# IPv4套接字地址结构
```c
struct in_addr {
    in_addr_t   s_addr;     /* 32-bit IPv4 address */
                            /* network byte ordered */

};

struct sockaddr_in {
    uint8_t         sin_len;    /* length of structure (16) */
    sa_family_t     sin_family; /* AF_INET */
    in_port_t       sin_port;   /* 16-bit TCP or UDP port number */
                                /* network byte ordered */
    struct in_addr  sin_addr;   /* 32-bit IPv4 address */
                                /* network byte ordered */
    char            sin_zero[8];    /* unused */
};
```
# 通用套接字地址结构
```c
struct sockaddr {
    uint8_t     sa_len;         
    sa_family_t sa_family;      /* address family: AF_xxx value */
    char        sa_data[14];    /* protocol-specific address */
};
```
# IPv6套接字地址结构
```c
struct in6_addr {
    uint8_t s6_addr[16];        /* 128-bit IPv6 address */
                                /* network byte ordered */
};

#define SIN6_LEN            /* required for compile-time tests */

struct sockaddr_in6 {
    uint8_t         sin6_len;       /* length of this struct (28) */
    sa_family_t     sin6_family;    /* AF_INET6 */
    in_port_t       sin6_port;      /* transport layer port# */
                                    /* network byte ordered */
    uint32_t        sin6_flowinfo;  /* flow information, undefined */
    struct in6_addr sin6_addr;      /* IPv6 address */
                                    /* network byte ordered */
    uint32_t        sin6_scope_id;  /* set of interfacess for a scope */
};
```

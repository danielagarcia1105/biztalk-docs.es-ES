---
title: "Configuración que puede modificarse para mejorar el rendimiento de red | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab8c4b32a5a5f588e76d155c2f8d052398f1a247
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a>Configuración que puede modificarse para mejorar el rendimiento de red
Este tema proporciona una descripción de los valores recomendados que afectan al rendimiento red.  
  
> [!IMPORTANT]  
>  Durante las pruebas de rendimiento completado para esta guía se ha observado que aparece Windows Server 2008 que se deben optimizar de forma predeterminada. Modificación de la configuración del registro sólo se debe realizar tras un cuidadoso análisis de los efectos en el sistema.  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a>Ajustar la configuración de puerto de usuario máximo y TcpTimedWaitDelay  
 El **MaxUserPort** valor controla el número de puerto máximo que se utiliza cuando una aplicación solicita un puerto de usuario disponible desde el sistema. Normalmente, los puertos de corta duración se asignan en el intervalo comprendido entre 1025 y 65535. El intervalo de puertos ahora es realmente un intervalo con un punto de partida y con un punto de conexión. El nuevo puerto de inicio predeterminado es 49152 y el puerto de extremo predeterminado es 65535. Este intervalo es además de los puertos conocidos que utilizan los servicios y aplicaciones. El intervalo de puertos que se usa los servidores puede modificarse en cada servidor. Ajustar este intervalo con el comando netsh, como se indica a continuación:  
  
 **netsh int \<ipv4 &#124; ipv6 > establecer puertos dinámicos \<tcp &#124; udp > iniciar = num número = intervalo**  
  
 Este comando establece el intervalo de puertos dinámicos para TCP. El puerto de inicio es **número**, y es el número total de puertos **intervalo**. Los siguientes son ejemplos de comandos: puede ver el intervalo de puertos dinámicos mediante los comandos netsh siguientes:  
  
-   netsh int ipv4 Mostrar puertos dinámicos tcp. Para aumentar el intervalo para el valor máximo permitido para tcp v4, utilice el siguiente comando:  
  
     **netsh int ipv4 Establecer inicio de puertos dinámicos tcp = 1025 num = 64511**  
  
-   netsh int ipv4 mostrar udp de puertos dinámicos  
  
-   netsh int ipv6 Mostrar puertos dinámicos tcp  
  
-   netsh int ipv6 mostrar udp de puertos dinámicos  
  
 El **TcpTimedWaitDelay** valor determina el período de tiempo que una conexión permanece en el estado TIME_WAIT cuando se está cerrando. Mientras una conexión está en el estado TIME_WAIT, no se puede reutilizar el par de Sockets. Se trata también conocido como el estado 2MSL porque el valor debe ser dos veces la duración máxima del segmento en la red. Para obtener más información, consulte [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719). Para ajustar la configuración de TcpTimedWaitDelay, tendrá que modificar la configuración del registro como se muestra a continuación:  
  
###  
  
|||  
|-|-|  
|Clave:|HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters|  
|Valor:|TcpTimedWaitDelay|  
|Tipo de datos:|REG_DWORD|  
|Intervalo:|30-300 (decimal)|  
|Valor predeterminado:|0 x 78 (120 en decimal)|  
|Valor recomendado:|30|  
|¿Valor existe de manera predeterminada?|**Ya no**, debe agregarse.|  
  
## <a name="see-also"></a>Vea también  
 [Directrices generales para mejorar el rendimiento de red](../technical-guides/general-guidelines-for-improving-network-performance.md)
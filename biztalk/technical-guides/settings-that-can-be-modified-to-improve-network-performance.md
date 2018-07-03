---
title: Configuración que puede modificarse para mejorar el rendimiento de red | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6aacc3-e697-4cc9-b937-73a2f54e733b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a21cc6339c82ab5465f117c8ef51d539add0055
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016263"
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a>Configuración que puede modificarse para mejorar el rendimiento de red
En este tema se proporciona una descripción de los valores recomendados que afectan al rendimiento de red.  
  
> [!IMPORTANT]  
>  Durante las pruebas de rendimiento completado para esta guía se ha observado que Windows Server 2008 parece ajustarse de forma predeterminada. Modificación de la configuración del registro solo debe realizarse tras un cuidadoso análisis de los efectos en el sistema.  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a>Ajuste la configuración MaxUserPort y TcpTimedWaitDelay  
 El **MaxUserPort** valor controla el número de puerto máximo que se usa cuando una aplicación solicita cualquier puerto disponible del usuario del sistema. Normalmente, se asignan los puertos de corta duración en el intervalo comprendido entre 1025 y 65535. El intervalo de puertos ahora es realmente un intervalo con un punto de partida y con un punto de conexión. El nuevo puerto de inicio predeterminado es el 49152 y el puerto final predeterminado es 65535. Este intervalo es además de los puertos conocidos que se usan servicios y aplicaciones. El intervalo de puertos que se usa los servidores puede modificarse en cada servidor. Ajustar este intervalo con el comando netsh, como sigue:  
  
 **netsh int \<ipv4&#124;ipv6\> establecer dinámicos \<tcp&#124;udp\> iniciar = num número = intervalo**  
  
 Este comando establece el intervalo de puertos dinámicos para TCP. El puerto de inicio es **número**, y es el número total de puertos **intervalo**. Los siguientes son ejemplos de comandos: puede ver el intervalo de puertos dinámicos mediante los comandos netsh siguientes:  
  
- netsh int ipv4 mostrar tcp dinámicos. Para aumentar el intervalo para el valor máximo permitido de tcp v4, use el siguiente comando:  
  
   **netsh int ipv4 establecer dinámicos tcp inicio = num 1025 = 64511**  
  
- netsh int ipv4 mostrar udp dinámicos  
  
- netsh int ipv6 mostrar dinámicos tcp  
  
- netsh int ipv6 mostrar udp dinámicos  
  
  El **TcpTimedWaitDelay** valor determina el período de tiempo que una conexión permanece en el estado TIME_WAIT al cerrarse. Aunque es una conexión en el estado TIME_WAIT, no se puede reutilizar el par de Sockets. También conocido como es el estado 2MSL porque el valor debe ser dos veces la duración máxima del segmento de la red. Para obtener más información, consulte [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (HYPERLINK "<http://go.microsoft.com/fwlink/?LinkId=113719>" <http://go.microsoft.com/fwlink/?LinkId=113719>). Para ajustar la configuración de TcpTimedWaitDelay, tendrá que modificar la configuración del registro como se muestra a continuación:  
  
###  
  
|||  
|-|-|  
|Clave:|HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters|  
|Valor:|TcpTimedWaitDelay|  
|Tipo de datos:|REG_DWORD|  
|Intervalo:|30-300 (decimal)|  
|Valor predeterminado:|0 x 78 (120 decimal)|  
|Valor recomendado:|30|  
|¿Valor existe de forma predeterminada?|**No**, debe agregarse.|  
  
## <a name="see-also"></a>Vea también  
 [Directrices generales para mejorar el rendimiento de red](../technical-guides/general-guidelines-for-improving-network-performance.md)
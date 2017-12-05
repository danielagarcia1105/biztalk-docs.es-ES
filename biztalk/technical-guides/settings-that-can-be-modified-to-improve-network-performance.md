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
ms.openlocfilehash: 8557c8bbe8c0b1c785d6da8d87e8950d3779b8d0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="settings-that-can-be-modified-to-improve-network-performance"></a><span data-ttu-id="45306-102">Configuración que puede modificarse para mejorar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="45306-102">Settings that can be Modified to Improve Network Performance</span></span>
<span data-ttu-id="45306-103">Este tema proporciona una descripción de los valores recomendados que afectan al rendimiento red.</span><span class="sxs-lookup"><span data-stu-id="45306-103">This topic provides a description of recommended values   that impact network performance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45306-104">Durante las pruebas de rendimiento completado para esta guía se ha observado que aparece Windows Server 2008 que se deben optimizar de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45306-104">During performance testing completed for this guide it was observed that Windows Server 2008 appears to be tuned by default.</span></span> <span data-ttu-id="45306-105">Modificación de la configuración del registro sólo se debe realizar tras un cuidadoso análisis de los efectos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="45306-105">Modification of  registry settings should only be done after a careful analysis of the effects on the system.</span></span>  
  
## <a name="adjust-the-maxuserport-and-tcptimedwaitdelay-settings"></a><span data-ttu-id="45306-106">Ajustar la configuración de puerto de usuario máximo y TcpTimedWaitDelay</span><span class="sxs-lookup"><span data-stu-id="45306-106">Adjust the MaxUserPort and TcpTimedWaitDelay settings</span></span>  
 <span data-ttu-id="45306-107">El **MaxUserPort** valor controla el número de puerto máximo que se utiliza cuando una aplicación solicita un puerto de usuario disponible desde el sistema.</span><span class="sxs-lookup"><span data-stu-id="45306-107">The **MaxUserPort** value controls the maximum port number used when an application requests any available user port from the system.</span></span> <span data-ttu-id="45306-108">Normalmente, los puertos de corta duración se asignan en el intervalo comprendido entre 1025 y 65535.</span><span class="sxs-lookup"><span data-stu-id="45306-108">Normally, short-lived ports are allocated in the range from 1025 through 65535.</span></span> <span data-ttu-id="45306-109">El intervalo de puertos ahora es realmente un intervalo con un punto de partida y con un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="45306-109">The port range is now truly a range with a starting point and with an endpoint.</span></span> <span data-ttu-id="45306-110">El nuevo puerto de inicio predeterminado es 49152 y el puerto de extremo predeterminado es 65535.</span><span class="sxs-lookup"><span data-stu-id="45306-110">The new default start port is 49152, and the default end port is 65535.</span></span> <span data-ttu-id="45306-111">Este intervalo es además de los puertos conocidos que utilizan los servicios y aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="45306-111">This range is in addition to well-known ports that are used by services and by applications.</span></span> <span data-ttu-id="45306-112">El intervalo de puertos que se usa los servidores puede modificarse en cada servidor.</span><span class="sxs-lookup"><span data-stu-id="45306-112">The port range that is used by the servers can be modified on each server.</span></span> <span data-ttu-id="45306-113">Ajustar este intervalo con el comando netsh, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="45306-113">You adjust this range by using the netsh command, as follows:</span></span>  
  
 <span data-ttu-id="45306-114">**netsh int \<ipv4 &#124; ipv6\> establecer puertos dinámicos \<tcp &#124; udp\> iniciar = num número = intervalo**</span><span class="sxs-lookup"><span data-stu-id="45306-114">**netsh int \<ipv4&#124;ipv6\> set dynamicport \<tcp&#124;udp\> start=number num=range**</span></span>  
  
 <span data-ttu-id="45306-115">Este comando establece el intervalo de puertos dinámicos para TCP.</span><span class="sxs-lookup"><span data-stu-id="45306-115">This command sets the dynamic port range for TCP.</span></span> <span data-ttu-id="45306-116">El puerto de inicio es **número**, y es el número total de puertos **intervalo**.</span><span class="sxs-lookup"><span data-stu-id="45306-116">The start port is **number**, and the total number of ports is **range**.</span></span> <span data-ttu-id="45306-117">Los siguientes son ejemplos de comandos: puede ver el intervalo de puertos dinámicos mediante los comandos netsh siguientes:</span><span class="sxs-lookup"><span data-stu-id="45306-117">The following are sample commands: You can view the dynamic port range by using the following netsh commands:</span></span>  
  
-   <span data-ttu-id="45306-118">netsh int ipv4 Mostrar puertos dinámicos tcp.</span><span class="sxs-lookup"><span data-stu-id="45306-118">netsh int ipv4 show dynamicport tcp.</span></span> <span data-ttu-id="45306-119">Para aumentar el intervalo para el valor máximo permitido para tcp v4, utilice el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="45306-119">To increase the range to the maximum allowed value for tcp v4, use the following command:</span></span>  
  
     <span data-ttu-id="45306-120">**netsh int ipv4 Establecer inicio de puertos dinámicos tcp = 1025 num = 64511**</span><span class="sxs-lookup"><span data-stu-id="45306-120">**netsh int ipv4 set dynamicport tcp start=1025 num=64511**</span></span>  
  
-   <span data-ttu-id="45306-121">netsh int ipv4 mostrar udp de puertos dinámicos</span><span class="sxs-lookup"><span data-stu-id="45306-121">netsh int ipv4 show dynamicport udp</span></span>  
  
-   <span data-ttu-id="45306-122">netsh int ipv6 Mostrar puertos dinámicos tcp</span><span class="sxs-lookup"><span data-stu-id="45306-122">netsh int ipv6 show dynamicport tcp</span></span>  
  
-   <span data-ttu-id="45306-123">netsh int ipv6 mostrar udp de puertos dinámicos</span><span class="sxs-lookup"><span data-stu-id="45306-123">netsh int ipv6 show dynamicport udp</span></span>  
  
 <span data-ttu-id="45306-124">El **TcpTimedWaitDelay** valor determina el período de tiempo que una conexión permanece en el estado TIME_WAIT cuando se está cerrando.</span><span class="sxs-lookup"><span data-stu-id="45306-124">The **TcpTimedWaitDelay** value determines the length of time that a connection stays in the TIME_WAIT state when being closed.</span></span> <span data-ttu-id="45306-125">Mientras una conexión está en el estado TIME_WAIT, no se puede reutilizar el par de Sockets.</span><span class="sxs-lookup"><span data-stu-id="45306-125">While a connection is in the TIME_WAIT state, the socket pair cannot be reused.</span></span> <span data-ttu-id="45306-126">Se trata también conocido como el estado 2MSL porque el valor debe ser dos veces la duración máxima del segmento en la red.</span><span class="sxs-lookup"><span data-stu-id="45306-126">This is also known as the 2MSL state because the value should be twice the maximum segment lifetime on the network.</span></span> <span data-ttu-id="45306-127">Para obtener más información, consulte [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) (HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719).</span><span class="sxs-lookup"><span data-stu-id="45306-127">For more information, see [Internet RFC 793](http://go.microsoft.com/fwlink/?LinkId=113719) ( HYPERLINK "http://go.microsoft.com/fwlink/?LinkId=113719" http://go.microsoft.com/fwlink/?LinkId=113719).</span></span> <span data-ttu-id="45306-128">Para ajustar la configuración de TcpTimedWaitDelay, tendrá que modificar la configuración del registro como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="45306-128">To adjust the TcpTimedWaitDelay settings, you have to modify the registry settings as listed below:</span></span>  
  
###  
  
|||  
|-|-|  
|<span data-ttu-id="45306-129">Clave:</span><span class="sxs-lookup"><span data-stu-id="45306-129">Key:</span></span>|<span data-ttu-id="45306-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span><span class="sxs-lookup"><span data-stu-id="45306-130">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters</span></span>|  
|<span data-ttu-id="45306-131">Valor:</span><span class="sxs-lookup"><span data-stu-id="45306-131">Value:</span></span>|<span data-ttu-id="45306-132">TcpTimedWaitDelay</span><span class="sxs-lookup"><span data-stu-id="45306-132">TcpTimedWaitDelay</span></span>|  
|<span data-ttu-id="45306-133">Tipo de datos:</span><span class="sxs-lookup"><span data-stu-id="45306-133">Data Type:</span></span>|<span data-ttu-id="45306-134">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="45306-134">REG_DWORD</span></span>|  
|<span data-ttu-id="45306-135">Intervalo:</span><span class="sxs-lookup"><span data-stu-id="45306-135">Range:</span></span>|<span data-ttu-id="45306-136">30-300 (decimal)</span><span class="sxs-lookup"><span data-stu-id="45306-136">30-300 (decimal)</span></span>|  
|<span data-ttu-id="45306-137">Valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="45306-137">Default value:</span></span>|<span data-ttu-id="45306-138">0 x 78 (120 en decimal)</span><span class="sxs-lookup"><span data-stu-id="45306-138">0x78 (120 decimal)</span></span>|  
|<span data-ttu-id="45306-139">Valor recomendado:</span><span class="sxs-lookup"><span data-stu-id="45306-139">Recommended value:</span></span>|<span data-ttu-id="45306-140">30</span><span class="sxs-lookup"><span data-stu-id="45306-140">30</span></span>|  
|<span data-ttu-id="45306-141">¿Valor existe de manera predeterminada?</span><span class="sxs-lookup"><span data-stu-id="45306-141">Value exists by default?</span></span>|<span data-ttu-id="45306-142">**Ya no**, debe agregarse.</span><span class="sxs-lookup"><span data-stu-id="45306-142">**No**, needs to be added.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45306-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="45306-143">See Also</span></span>  
 [<span data-ttu-id="45306-144">Directrices generales para mejorar el rendimiento de red</span><span class="sxs-lookup"><span data-stu-id="45306-144">General Guidelines for Improving Network Performance</span></span>](../technical-guides/general-guidelines-for-improving-network-performance.md)
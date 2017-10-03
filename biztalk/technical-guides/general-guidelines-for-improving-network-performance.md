---
title: Directrices generales para mejorar el rendimiento de red | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 286c10d2-9262-4e3c-adde-f7b5780c2736
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67b76a7e488610a72952832d2a84526ca60d6989
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="general-guidelines-for-improving-network-performance"></a>Directrices generales para mejorar el rendimiento de red
Ajustar la configuración de red para los valores óptimos ha demostrado a solucionar los cuellos de botella de red y mejorar el rendimiento general de red en las soluciones de BizTalk Server. Esto debe realizarse en todos los equipos que participan en la solución, incluidos los equipos con BizTalk Server, los equipos de SQL Server y cualquier otro equipo de servidor.  
  
> [!NOTE]  
>  La indicación más frecuente que las E/S de red es un cuello de botella en un entorno de BizTalk Server es el contador "SQL Server: espera Statistics\Network E/S espera". Cuando el valor de **promedio de tiempo de espera** en este contador es mayor que cero en uno o varios de los equipos de SQL Server, y E/S de red es un cuello de botella.  
  
 La recomendación siguiente puede utilizarse para aumentar el rendimiento de red:  
  
## <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a>Agregar tarjetas de red adicionales a los equipos en el entorno de BizTalk Server  
 Basta con agregar como unidades de disco duro adicionales pueden mejorar el rendimiento de disco, agregar tarjetas de red adicionales pueden mejorar el rendimiento de la red. Si las tarjetas de red en los equipos de su entorno de BizTalk Server están saturadas y la tarjeta es un cuello de botella, considere la posibilidad de agregar uno o más tarjetas de red adicionales para mejorar el rendimiento.  
  
## <a name="implement-network-segmentation"></a>Implementar la segmentación de la red  
 Siga las recomendaciones de la **subredes** sección de la [notas del producto "Optimización de base de datos de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).  
  
## <a name="where-possible-replace-hubs-with-switches"></a>Siempre que sea posible, reemplace los concentradores con modificadores  
 Conmutadores contienen lógica para enrutar directamente el tráfico entre el origen y destino, mientras que los centros de usan un modelo para enrutar el tráfico de difusión. Por lo tanto, los conmutadores son más eficaces y ofrecen un mejor rendimiento.  
  
## <a name="remove-unnecessary-network-protocols"></a>Quitar protocolos de red innecesarios  
 Equipos con Windows Server a veces tengan más servicios de red y protocolos instalados que son realmente necesarios. Cada protocolo, servicio o cliente de red adicional coloca más sobrecarga de recursos del sistema.  
Además, cada protocolo instalado genera tráfico de red. Mediante la eliminación de protocolos, servicios y clientes de red innecesarias, los recursos del sistema se ponen a disposición de otros procesos, se evita el exceso de tráfico de red y el número de enlaces de red que se debe negociar se reduce al mínimo.  
Para ver los clientes de red instalados actualmente, protocolos y servicios, siga estos pasos:  
  
1.  Haga clic en **iniciar**y, a continuación, haga clic en **el Panel de Control**.  
  
2.  En el Panel de Control, realice una de las siguientes acciones  
  
    1.  En **ajustar la configuración del equipo**, establezca **ver** a **categoría**, haga clic en **red e Internet**y, a continuación, haga clic en  **Redes y recursos compartidos Center**.  
  
    2.  En **ajustar la configuración del equipo**, establezca **ver** como **iconos grandes** o **iconos pequeños**y, a continuación, haga clic en  **Redes y recursos compartidos Center**.  
  
3.  En el panel de tareas, haga clic en **cambiar configuración del adaptador**.  
  
4.  Haga clic en **conexión de área Local** (o la entrada para la conexión de red) y, a continuación, haga clic en **propiedades** para mostrar el cuadro de diálogo de propiedades para la conexión de red.  
  
5.  Para quitar un elemento innecesario, selecciónelo y haga clic en **desinstalar**. Para deshabilitar un elemento, simplemente desactive la casilla asociada al elemento.  
  
 Si no está seguro acerca de los efectos de la desinstalación de un elemento para la conexión, deshabilite el elemento en lugar de desinstalarlo. Deshabilitar elementos permite determinar qué servicios, protocolos y los clientes son realmente necesarios en un sistema. Cuando se ha determinado que deshabilitar un elemento no tiene ningún efecto adverso en el servidor, a continuación, se puede desinstalar el elemento.  
En muchos casos, solo los tres componentes siguientes son necesarios para la operación en una red TCP/IP según estándar:  
  
-   Cliente para redes Microsoft  
  
-   Compartir archivos e impresoras para redes Microsoft  
  
-   Protocolo de Internet (TCP/IP)  
  
## <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a>Controladores de adaptadores de red en todos los equipos en el entorno de BizTalk Server deben optimizarse para rendimiento  
  
> [!IMPORTANT]  
>  Antes de aplicar la optimización en controladores de adaptador de red siempre instalar a los controladores más recientes de dispositivo de adaptador de red para las tarjetas de red en el entorno.  
  
 Ajustar los controladores de dispositivo del adaptador de red para maximizar la cantidad de memoria disponible para el almacenamiento en búfer en paquetes tanto entrante como saliente. También maximizar recuentos de búfer, especialmente búferes de transmisión y búferes de unión. Los valores predeterminados para estos parámetros y si se proporcionan incluso, varían entre los fabricantes y las versiones del controlador. El objetivo es maximizar el trabajo realizado por el hardware del adaptador de red y para permitir que el mayor espacio de búfer para las operaciones de red mitigar ráfagas de tráfico de red y la congestión asociada.  
  
> [!NOTE]  
>  Pasos para optimizar los controladores de adaptador de red varían según el fabricante.  
  
 Siga estos pasos para tener acceso a la configuración de los adaptadores de red:  
  
1.  Haga clic en **iniciar** y, a continuación, haga clic en **el Panel de Control**.  
  
2.  En el Panel de Control, realice una de las siguientes acciones:  
  
    1.  En **ajustar la configuración del equipo**, establezca **ver** a **categoría**, haga clic en **red e Internet**y, a continuación, haga clic en  **Redes y recursos compartidos Center**.  
  
    2.  En **ajustar la configuración del equipo**, establezca **ver** como **iconos grandes** o **iconos pequeños**y, a continuación, haga clic en  **Redes y recursos compartidos Center**.  
  
3.  En el panel de tareas, haga clic en **cambiar configuración del adaptador**.  
  
4.  Haga clic en **conexión de área Local** (o el nombre de la conexión de red) y, a continuación, haga clic en **propiedades**.  
  
5.  En el **red** , haga clic en **configurar**.  
  
6.  Haga clic en el **avanzadas** ficha a las propiedades de acceso que se pueden configurar para el adaptador de red.  
  
 Las siguientes propiedades se deben configurar para cada adaptador de red en el entorno de BizTalk Server:  
  
> [!NOTE]  
>  Aplicar esta configuración para cada adaptador de red físico, incluidos los adaptadores de red individuales dentro de un conjunto en equipo de adaptadores de red que están configurados para la agregación, equilibrio de carga y tolerancia a errores. Con algunos programas de software de formación de equipos, deberá aplicar esta configuración en el equipo también. Tenga en cuenta que algunos adaptadores de red son autoajustables y no podrán usar la opción para configurar los parámetros manualmente.  
  
-   **Opción de energía** : configurar el controlador de adaptador de red para impedir que la funcionalidad de administración de energía al desactivar el adaptador de red para ahorrar energía. Esta funcionalidad puede ser útil para los equipos cliente, pero debe rara vez, si alguna vez, puede usar en un equipo de BizTalk Server o SQL Server.  
  
-   **Fija la velocidad y dúplex (no utilice AUTO)** -es muy importante que la velocidad de la red, dúplex y parámetros de control de flujo se establecen de acuerdo con la configuración en el conmutador al que está conectados. Esto mitigará la aparición de "auto-sincronización periódica" lo que puede tardar temporalmente las conexiones fuera de línea.  
  
-   **Max fusionar búferes** -registros de mapa son recursos del sistema utilizados para convertir direcciones físicas para direcciones virtuales para los adaptadores de red que admiten el control por bus. Fusionar los búferes están disponibles para el controlador de red si el controlador se ejecuta fuera de los registros de mapa. Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto podría tener un negativo impacto como búferes de unión consumen memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Descriptores de transmisión y envío de Max y búferes de envío** -esta configuración especifica cuántos asigna el controlador para su uso por la interfaz de red de búferes de control de transmisión. Esto refleja directamente el número de paquetes pendientes que el controlador puede tener en su cola de "envío". Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto puede tener un impacto negativo como búferes de envío consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Búferes de recepción de max** -esta configuración especifica la cantidad de búfer de memoria utilizado por el controlador de interfaz de red cuando se copian datos a la memoria de protocolo. Normalmente se establece de forma predeterminada en un valor relativamente bajo. Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto podría tener un negativo impacto como búferes de recepción consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Todas las opciones de descarga en** : en casi todos los casos, el rendimiento mejora al habilitar características de descarga de interfaz de red. Algunos adaptadores de red proporcionan parámetros separados para habilitar o deshabilitar la descarga para enviar y recibir tráfico. Descargar las tareas de la CPU para el adaptador de red puede ayudar a un menor uso de CPU en el servidor que mejorará el rendimiento general del sistema. El transporte de Microsoft TCP/IP puede descargar una o varias de las siguientes tareas para un adaptador de red que tenga las capacidades adecuadas:  
  
    -   **Tareas de suma de comprobación** : transporte del TCP/IP puede descargar el cálculo y validación de las sumas de comprobación IP y TCP para envía y recibe al adaptador de red; habilite esta opción si el controlador de adaptador de red proporciona esta capacidad.  
  
    -   **Las tareas de seguridad IP** -transporte del TCP/IP puede descargar el cálculo y la validación de las sumas de comprobación cifrado para los encabezados de autenticación (AH) y encapsuladora (ESP) de cargas de seguridad para el adaptador de red. El transporte de TCP/IP también puede descargar el cifrado y descifrado de cargas de ESP al adaptador de red. Habilitar estas opciones si el controlador de adaptador de red proporciona esta capacidad.  
  
    -   **Segmentación de los paquetes TCP grandes** -transporte del TCP/IP es compatible con la descarga de envío grande (LSO). Con LSO, el transporte de TCP/IP puede descargar la segmentación de los paquetes TCP grandes.  
  
    -   **Descarga de la pila** : la pila de toda la red se pueden descargar en un adaptador de red que tenga las capacidades adecuadas. Habilite esta opción si el controlador de adaptador de red proporciona esta capacidad.  
  
-   **Wake On LAN deshabilitado (a menos que se usan)** : configurar el controlador de adaptador de red para deshabilitar la funcionalidad de lan wake-on. Esta funcionalidad puede ser útil para los equipos cliente, pero rara vez si alguna vez se debe utilizar en un equipo de BizTalk Server o SQL Server.  
  
 Para obtener más información acerca del ajuste de los adaptadores de red para el rendimiento, consulte el **configuración de dispositivo de red** sección de la [notas del producto "Optimización de base de datos de BizTalk Server"](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).  
  
## <a name="see-also"></a>Vea también  
 [Configuración que puede modificarse para mejorar el rendimiento de red](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)
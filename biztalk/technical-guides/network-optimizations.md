---
title: Optimizaciones de red | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ff0392f-37ae-4ca6-8cc6-d53065de64c5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66419a1c864b4c22d4fb28a70c85cabf2eceb1a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994797"
---
# <a name="network-optimizations"></a>Optimizaciones de red
En un entorno de BizTalk Server donde los equipos de BizTalk Server son independientes de los equipos de SQL Server, cada uno de los mensajes procesados por BizTalk Server requiere comunicación a través de la red. Esta comunicación incluye tráfico considerable entre los equipos de BizTalk Server y las bases de datos de cuadro de mensaje de BizTalk, las bases de datos de administración de BizTalk, las bases de datos BAM y otras bases de datos. En escenarios de carga alta, esta comunicación puede provocar mucho tráfico de red y puede convertirse en un cuello de botella, especialmente cuando la configuración de red no se han optimizado, no hay suficientes tarjetas de interfaz de red se instalan o no hay suficiente ancho de banda es está disponible.  
  
 Este tema proporciona los pasos para mejorar el rendimiento de red entre máquinas virtuales de Hyper-V que se ejecutan en el mismo equipo host de Hyper-V y proporciona algunas recomendaciones generales para mejorar el rendimiento de red.  
  
> [!NOTE]  
>  El indicador más comunes que E/S de red es un cuello de botella es el contador "Esperas de SQL Server: espera Statistics\Network E/S". Cuando el valor de **promedio de tiempo de espera** en este contador es mayor que cero en uno o varios de los equipos de SQL Server, E/S de red es un cuello de botella.  
  
## <a name="improving-network-performance-of-biztalk-server-on-hyper-v"></a>Mejorar el rendimiento de red del servidor BizTalk Server en Hyper-V  
  
### <a name="configure-hyper-v-virtual-machines-that-are-running-on-the-same-hyper-v-host-computer-to-use-a-private-virtual-network"></a>Configurar máquinas virtuales de Hyper-V que se ejecutan en el mismo equipo host de Hyper-V para usar una red de privada Virtual  
 Para mejorar el rendimiento de red entre máquinas virtuales de Hyper-V que se ejecutan en el mismo equipo host de Hyper-V, cree un virtual de red y enrutar tráfico de redes privadas entre máquinas virtuales a través de la red virtual privada.  
  
##### <a name="create-a-private-virtual-network"></a>Crear una red privada Virtual  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**. Haga clic en **herramientas administrativas**y, a continuación, haga clic en **Administrador de Hyper-V**.  
  
2.  En el panel izquierdo del Administrador de Hyper-V, haga clic en **Administrador de Hyper-V**y, a continuación, haga clic en **conectar al servidor**.  
  
3.  En el **Seleccionar equipo** cuadro de diálogo, escriba el nombre del equipo host de Hyper-V y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel izquierdo del Administrador de Hyper-V, haga clic en el host de Hyper-V y, a continuación, haga clic en **Administrador de redes virtuales**.  
  
5.  En el Administrador de red Virtual, en **qué tipo de red virtual desea crear?**, haga clic en **privada**y, a continuación, haga clic en **agregar**.  
  
6.  Escriba un nombre para la nueva red virtual y, a continuación, haga clic en **Aceptar**. Ahora está disponible para cada máquina virtual de Hyper-V que se ejecuta en este host de Hyper-V la red virtual.  
  
##### <a name="add-the-private-virtual-network-to-hyper-v-virtual-machines-running-on-the-hyper-v-host"></a>Agregar a la red Virtual privada a Hyper-V Virtual Machines que se ejecutan en el Host de Hyper-V  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**. Haga clic en **herramientas administrativas**y, a continuación, haga clic en **Administrador de Hyper-V**.  
  
2.  En el panel izquierdo del Administrador de Hyper-V, haga clic en **Administrador de Hyper-V**y, a continuación, haga clic en **conectar al servidor**.  
  
3.  En el **Seleccionar equipo** cuadro de diálogo, escriba el nombre del equipo host de Hyper-V y, a continuación, haga clic en **Aceptar**.  
  
4.  Apagar las máquinas virtuales en ejecución para el que desea agregar la red virtual privada con el botón secundario en la máquina virtual y, a continuación, haciendo clic en **apagar**.  
  
5.  Después de apagar las máquinas virtuales, haga clic en una máquina virtual y, a continuación, haga clic en **configuración** para cambiar la configuración de una máquina virtual.  
  
6.  En el **configuración para < nombre_equipo >** cuadro de diálogo **agregar Hardware**, haga clic para seleccionar **adaptador de red**y, a continuación, haga clic en **agregar**.  
  
7.  En el **adaptador de red** página de configuración, en **red:**, seleccione la red privada virtual que creó anteriormente y, a continuación, haga clic en **Aceptar**. Ahora ha realizado la red privada virtual disponible para la máquina virtual de Hyper-V que estará accesible la próxima vez que se inicia la máquina virtual.  
  
8.  Repita los pasos anteriores para cada máquina virtual para el que desea enrutar el tráfico de red a través de la red virtual privada.  
  
9. Iniciar las máquinas virtuales que se ha agregado a la red privada virtual. Haga clic en cada máquina virtual y haga clic en **iniciar**.  
  
##### <a name="configure-each-virtual-machine-to-use-the-private-virtual-network"></a>Configuración de cada máquina Virtual para usar la red Virtual privada  
  
1.  Una vez que se inició cada máquina virtual, la red virtual privada es accesible para la máquina virtual como una conexión de red. Configurar la conexión de red en cada máquina virtual para usar TCP/IPv4 y especifique la configuración para el protocolo TCP/IPv4.  
  
    1.  Obtener acceso a la página de propiedades de conexión de red, seleccione **4(TCP/IPv4) de protocolo de Internet versión**y, a continuación, haga clic en **propiedades**.  
  
    2.  Haga clic en el botón de radio junto a **usar la siguiente dirección IP**.  
  
2.  Escriba un valor para el **dirección IP** campo desde el intervalo de dirección IP privada aborda identificado en "RFC 1918, asignación de direcciones para las direcciones IP privadas" en [ http://go.microsoft.com/fwlink/?LinkID=31904 ](http://go.microsoft.com/fwlink/?LinkID=31904).  
  
3.  Tome nota de la dirección IP que especificó; deberá asociar este valor con el nombre de NetBIOS del equipo en una entrada de archivo de HOSTS más adelante.  
  
4.  Escriba un valor adecuado para el **máscara de subred** campo.  
  
    > [!NOTE]  
    >  Windows deben rellenar el **máscara de subred** campo con un valor adecuado en función del valor que ha introducido en el **dirección IP** campo.  
  
5.  Deje el **puerta de enlace predeterminada** haga clic en de campo en blanco, **Aceptar**y, a continuación, haga clic en **cerrar**.  
  
6.  Después de configurar cada máquina virtual con una única dirección IP privada, actualice el archivo de HOSTS en cada máquina virtual con la dirección IP y el nombre de NetBIOS de las otras máquinas virtuales que se ejecutan en el equipo host de Hyper-V. En cada máquina virtual, se debe guardar el archivo de HOSTS actualizado a la carpeta %systemroot%\drivers\etc\.  
  
    > [!NOTE]  
    >  Dado que de forma predeterminada, Windows comprueba el archivo HOSTS local primero para resolver nombres NetBIOS, actualizando el archivo de HOSTS en cada máquina virtual con las direcciones IP privadas únicas de las otras máquinas virtuales, tráfico de red entre estos máquina ahora se enrutarán a través la red privada virtual.  
  
### <a name="disable-tcp-offloading-for-the-virtual-machine-network-cards"></a>Deshabilitar la descarga de TCP para las tarjetas de red de máquina Virtual  
 Editar el registro como se describe en el tema de MSDN "Mediante los valores del registro para habilitar y deshabilitar la tarea Offloading (NDIS 5.1)" en [ http://go.microsoft.com/fwlink/?LinkId=147619 ](http://go.microsoft.com/fwlink/?LinkId=147619) para deshabilitar la descarga de TCP para las tarjetas de red en cada máquina virtual.  
  
> [!IMPORTANT]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base "Descripción del registro de Microsoft Windows" en [ http://go.microsoft.com/fwlink/?LinkId=62729 ](http://go.microsoft.com/fwlink/?LinkId=62729).  
  
## <a name="general-guidelines-for-improving-network-performance"></a>Directrices generales para mejorar el rendimiento de red  
 Las recomendaciones siguientes pueden utilizarse para aumentar el rendimiento de red:  
  
### <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a>Agregar tarjetas de red adicionales a los equipos en el entorno de BizTalk Server  
 Basta con agregar como unidades de disco duro adicionales pueden mejorar el rendimiento de disco, agregar tarjetas de red adicionales pueden mejorar el rendimiento de la red. Si están saturadas las tarjetas de red en los equipos en su entorno de BizTalk Server y la tarjeta es un cuello de botella, considere la posibilidad de agregar uno o más tarjetas de red adicionales para mejorar el rendimiento.  
  
### <a name="implement-network-segmentation"></a>Implementar la segmentación de la red  
 Siga las recomendaciones de la **subredes** sección de las notas del producto "Optimización de base de datos de BizTalk Server" en [ http://go.microsoft.com/fwlink/?LinkID=101578 ](http://go.microsoft.com/fwlink/?LinkID=101578).  
  
### <a name="where-possible-replace-hubs-with-switches"></a>Siempre que sea posible, reemplace concentradores con modificadores  
 Conmutadores contienen lógica para enrutar directamente el tráfico entre el origen y destino, mientras que hubs usa un modelo para enrutar el tráfico de difusión. Por lo tanto, los conmutadores son más eficaces y ofrecen un mejor rendimiento.  
  
### <a name="remove-unnecessary-network-protocols"></a>Quitar protocolos de red innecesarios  
 Equipos con Windows Server a veces tienen más de los servicios de red y protocolos instalados que se requieren en realidad. Cada protocolo, servicio o cliente de red adicional coloca más sobrecarga en los recursos del sistema.  
  
 Además, cada protocolo instalado genera tráfico de red. Mediante la eliminación de protocolos, servicios y clientes de red innecesario, los recursos del sistema se encuentran disponibles para otros procesos, se evita el exceso de tráfico de red y el número de enlaces de red que se debe negociar se reduce al mínimo.  
  
 Para ver los clientes de red instalados actualmente, protocolos y servicios, siga estos pasos:  
  
1. Haga clic en **iniciar**, apunte a **configuración**y, a continuación, haga clic en **Panel de Control**.  
  
2. Haga doble clic en **las conexiones de red** para mostrar las conexiones de red en el equipo.  
  
3. Haga clic en **Local Area Connection** (o la entrada para la conexión de red) y, a continuación, haga clic en **propiedades** para mostrar el cuadro de diálogo de propiedades para la conexión de red.  
  
4. Para quitar un elemento innecesario, selecciónelo y haga clic en **desinstalar**. Para deshabilitar un elemento, basta con que borre la casilla de verificación asociada con el elemento.  
  
   Si no está seguro acerca de los efectos de la desinstalación de un elemento para la conexión, deshabilite el elemento en lugar de desinstalarlo. Deshabilitar elementos permite determinar qué servicios, protocolos y los clientes son realmente necesarias en un sistema. Cuando se ha determinado que deshabilitar un elemento no tiene ningún efecto adverso en el servidor, a continuación, se puede desinstalar el elemento.  
  
   En muchos casos, solo los tres componentes siguientes son necesarios para la operación en una red en función de TCP/IP estándar:  
  
-   Cliente para redes Microsoft  
  
-   Compartir archivos e impresoras para redes Microsoft  
  
-   Protocolo de Internet (TCP/IP)  
  
### <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a>Controladores de adaptador de red en todos los equipos en el entorno de BizTalk Server deben optimizarse para rendimiento  
  
> [!IMPORTANT]  
>  Antes de aplicar la optimización a controladores de adaptador de red, instale siempre los últimos controladores de dispositivo de adaptador de red para las tarjetas de red en el entorno.  
  
 Ajustar los controladores de dispositivo del adaptador de red para maximizar la cantidad de memoria disponible para el almacenamiento en búfer en el paquete, entrante y saliente. También maximizar recuentos de búfer, especialmente los búferes de transmisión y búferes de unión. Los valores predeterminados para estos parámetros y si incluso se proporcionan, variar entre los fabricantes y las versiones del controlador. El objetivo es maximizar el trabajo realizado por el hardware del adaptador de red y para permitir que el mayor espacio de búfer para las operaciones de red mitigar las ráfagas de tráfico de red y la congestión asociada.  
  
> [!NOTE]  
>  Pasos para optimizar los controladores de adaptador de red varían según el fabricante.  
  
 Siga estos pasos para tener acceso a configuración para adaptadores de red en[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]:  
  
1. Haga clic en **iniciar**,, y, a continuación, haga clic en **Panel de Control**.  
  
2. Haga clic en **red e Internet**y, a continuación, haga clic en **centro de redes y recursos compartidos**.  
  
3. Haga clic en **cambiar configuración del adaptador**, haga clic en **Local Area Connection** (o el nombre de la conexión de red) y, a continuación, haga clic en **propiedades**.  
  
4. En el **General** , haga clic **configurar**.  
  
5. Haga clic en el **avanzadas** ficha a las propiedades de acceso que se pueden configurar para el adaptador de red.  
  
   Las siguientes propiedades se deben configurar para cada adaptador de red en el entorno de BizTalk Server:  
  
> [!NOTE]  
>  Aplicar esta configuración para cada adaptador de red física, incluidos los adaptadores de red individuales dentro de un conjunto de adaptadores de red que están configurados para la tolerancia a errores, equilibrio de carga o agregación agrupado. Con algunos programas de formación de equipos, deberá aplicar esta configuración en el equipo también. Tenga en cuenta que algunos adaptadores de red son autoajustables y no se pueden ofrecer la opción para configurar los parámetros manualmente.  
  
- **Opción de energía** : configurar el controlador de adaptador de red para impedir que la funcionalidad de administración de energía al desactivar el adaptador de red para ahorrar energía. Esta funcionalidad puede ser útil para los equipos cliente, pero debe rara vez, si alguna vez, se utiliza en un equipo de BizTalk Server o SQL Server.  
  
- **Se ha corregido la velocidad y dúplex (no utilice AUTO)** -es muy importante que la velocidad de la red, dúplex y parámetros de flujo de control se establecen para que coincida con la configuración en el conmutador al que está conectados. Esto mitigará la aparición de "auto-sincronización periódica" lo que puede tardar temporalmente las conexiones fuera de línea.  
  
- **Max Coalesce Buffers** -registros de mapa son los recursos del sistema utilizados para convertir las direcciones físicas a las direcciones virtuales para los adaptadores de red que admiten el control por bus. Fusione los búferes están disponibles para el controlador de red si el controlador se ejecuta fuera de registros de mapa. Establezca este valor más alto posible para un rendimiento máximo. En los servidores con memoria física limitada, esto puede tener un valor negativo impacto como búferes de unión consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo se puede aplicar sin reducir significativamente la memoria disponible.  
  
- **Los descriptores de transmisión/envío máximo y los búferes de envío** -esta configuración especifica cuántos asigna el controlador para su uso por la interfaz de red de búferes de control de transmisión. Esto refleja el número de paquetes pendientes, que el controlador puede tener en su cola de "Enviar". Establezca este valor más alto posible para un rendimiento máximo. En los servidores con memoria física limitada, esto puede tener un impacto negativo como búferes de envío consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo se puede aplicar sin reducir significativamente la memoria disponible.  
  
- **Los búferes de recepción máxima** -esta configuración especifica la cantidad de búfer de memoria utilizado por el controlador de interfaz de red al copiar datos en la memoria de protocolo. Normalmente se establece de forma predeterminada en un valor relativamente bajo. Establezca este valor más alto posible para un rendimiento máximo. En los servidores con memoria física limitada, esto puede tener un valor negativo impacto, como los búferes de recepción consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo se puede aplicar sin reducir significativamente la memoria disponible.  
  
- **Todas las opciones de descarga en** - en casi todos los casos, el rendimiento mejora al habilitar las características de descarga de interfaz de red. Algunos adaptadores de red proporcionan parámetros independientes para habilitar o deshabilitar la descarga para enviar y recibir tráfico. Descargar las tareas de la CPU para el adaptador de red puede ayudar a menor uso de CPU en el servidor que mejorará el rendimiento general del sistema. El transporte de Microsoft TCP/IP puede descargar una o varias de las siguientes tareas para un adaptador de red que tenga las capacidades adecuadas:  
  
  -   **Tareas de la suma de comprobación** : transporte de The TCP/IP puede descargar el cálculo y validación de sumas de comprobación IP y TCP para envía y recibe el adaptador de red, habilite esta opción si el controlador de adaptador de red ofrece esta funcionalidad.  
  
  -   **Tareas de seguridad IP** -transporte del TCP/IP puede descargar el cálculo y la validación de sumas de comprobación de cifrado para los encabezados de autenticación (AH) y encapsuladora (ESP) de cargas de seguridad para el adaptador de red. El transporte de TCP/IP también puede descargar el cifrado y descifrado de cargas útiles de ESP para el adaptador de red. Habilitar estas opciones si el controlador de adaptador de red ofrece esta funcionalidad.  
  
  -   **Segmentación de los paquetes TCP grandes** -transporte del TCP/IP es compatible con la descarga de envío grande (LSO). Con LSO, el transporte de TCP/IP puede descargar la segmentación de los paquetes TCP grandes.  
  
  -   **Descarga de la pila** : la pila de toda la red puede descargarse en un adaptador de red que tenga las capacidades adecuadas. Habilite esta opción si el controlador de adaptador de red ofrece esta funcionalidad.  
  
- **Wake On LAN deshabilitadas (a menos que se usa)** : configurar el controlador de adaptador de red para deshabilitar la funcionalidad wake-on lan. Esta funcionalidad puede ser útil para los equipos cliente, pero rara vez si alguna vez se debe usar en un equipo de BizTalk Server o SQL Server.  
  
  Para obtener más información sobre el ajuste de los adaptadores de red para el rendimiento, consulte el **configuración de dispositivo de red** sección de las notas del producto "Optimización de base de datos de BizTalk Server" en [ http://go.microsoft.com/fwlink/?LinkID=101578 ](http://go.microsoft.com/fwlink/?LinkID=101578).
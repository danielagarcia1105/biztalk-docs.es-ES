---
title: Optimizaciones de red | Documentos de Microsoft
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
ms.openlocfilehash: bbf4b0e8df9d8baa81a91576dc37fd89413714f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298764"
---
# <a name="network-optimizations"></a>Optimizaciones de red
En un entorno de BizTalk Server donde los equipos de BizTalk Server son independientes de los equipos de SQL Server, cada mensaje procesado por el servidor BizTalk Server requiere comunicación a través de la red. Esta comunicación incluye el tráfico considerable entre los equipos de BizTalk Server y las bases de datos de cuadro de mensaje de BizTalk, las bases de datos de administración de BizTalk, las bases de datos BAM y otras bases de datos. En escenarios de carga elevada, esta comunicación, puede dar lugar a que el tráfico de red considerable y puede convertirse en un cuello de botella, especialmente cuando no se han optimizado configuración de red, no hay suficientes tarjetas de interfaz de red se instalan o no hay suficiente ancho de banda es está disponible.  
  
 Este tema proporciona los pasos necesarios para mejorar el rendimiento de red entre las máquinas virtuales Hyper-V se ejecuta en el mismo equipo host de Hyper-V y proporciona algunas recomendaciones generales para mejorar el rendimiento de la red.  
  
> [!NOTE]  
>  La indicación más frecuente que las E/S de red es un cuello de botella es el contador "SQL Server: espera Statistics\Network E/S espera." Cuando el valor de **promedio de tiempo de espera** en este contador es mayor que cero en uno o varios de los equipos de SQL Server, y E/S de red es un cuello de botella.  
  
## <a name="improving-network-performance-of-biztalk-server-on-hyper-v"></a>Mejorar el rendimiento de red del servidor BizTalk Server en Hyper-V  
  
### <a name="configure-hyper-v-virtual-machines-that-are-running-on-the-same-hyper-v-host-computer-to-use-a-private-virtual-network"></a>Configurar las máquinas virtuales de Hyper-V que se ejecutan en el mismo equipo host de Hyper-V para usar una red de Virtual privada  
 Para mejorar el rendimiento de red entre las máquinas virtuales Hyper-V que se ejecutan en el mismo equipo de host de Hyper-V, cree un privada tráfico de red de red y la ruta virtual entre máquinas virtuales a través de la red privada virtual.  
  
##### <a name="create-a-private-virtual-network"></a>Crear una red Virtual privada  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**. Haga clic en **herramientas administrativas**y, a continuación, haga clic en **Administrador de Hyper-V**.  
  
2.  En el panel izquierdo del Administrador de Hyper-V, haga clic en **Administrador de Hyper-V**y, a continuación, haga clic en **conectar con el servidor**.  
  
3.  En el **Seleccionar equipo** cuadro de diálogo, escriba el nombre del equipo de host de Hyper-V y, a continuación, haga clic en **Aceptar**.  
  
4.  En el panel izquierdo del Administrador de Hyper-V, haga clic en el host de Hyper-V y, a continuación, haga clic en **Administrador de redes virtuales**.  
  
5.  En el Administrador de red Virtual, en **qué tipo de red virtual desea crear?**, haga clic en **privada**y, a continuación, haga clic en **agregar**.  
  
6.  Escriba un nombre para la nueva red virtual y, a continuación, haga clic en **Aceptar**. Ahora está disponible para cada máquina virtual de Hyper-V que se ejecuta en este host de Hyper-V la red virtual.  
  
##### <a name="add-the-private-virtual-network-to-hyper-v-virtual-machines-running-on-the-hyper-v-host"></a>Agregar a la red Virtual privada para Hyper-V máquinas virtuales que ejecutan en el Host de Hyper-V  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**. Haga clic en **herramientas administrativas**y, a continuación, haga clic en **Administrador de Hyper-V**.  
  
2.  En el panel izquierdo del Administrador de Hyper-V, haga clic en **Administrador de Hyper-V**y, a continuación, haga clic en **conectar con el servidor**.  
  
3.  En el **Seleccionar equipo** cuadro de diálogo, escriba el nombre del equipo de host de Hyper-V y, a continuación, haga clic en **Aceptar**.  
  
4.  Apagar las máquinas virtuales en ejecución para el que desea agregar la red virtual privada con el botón secundario en la máquina virtual y, a continuación, haciendo clic en **apagar**.  
  
5.  Después de apagar las máquinas virtuales, haga clic en una máquina virtual y, a continuación, haga clic en **configuración** para cambiar la configuración de una máquina virtual.  
  
6.  En el **configuración de < nombre_equipo >** cuadro de diálogo **agregar Hardware**, haga clic para seleccionar **adaptador de red**y, a continuación, haga clic en **agregar**.  
  
7.  En el **adaptador de red** página de configuración, en **red:**, seleccione la red privada virtual que creó anteriormente y, a continuación, haga clic en **Aceptar**. Ahora ha realizado la red privada virtual disponible para la máquina virtual de Hyper-V que será accesible la próxima vez que se inicia la máquina virtual.  
  
8.  Repita los pasos anteriores para cada máquina virtual para la que desea redirigir el tráfico de red a través de la red privada virtual.  
  
9. Iniciar las máquinas virtuales que se ha agregado a la red privada virtual. Haga clic en cada máquina virtual y haga clic en **iniciar**.  
  
##### <a name="configure-each-virtual-machine-to-use-the-private-virtual-network"></a>Configurar cada máquina Virtual para usar la red Virtual privada  
  
1.  Una vez que se inició cada máquina virtual, la red virtual privada es accesible para la máquina virtual como una conexión de red. Configurar la conexión de red en cada máquina virtual para usar TCP/IPv4 y especifique la configuración para el protocolo TCP/IPv4.  
  
    1.  Obtener acceso a la página de propiedades de conexión de red, seleccione **4(TCP/IPv4) de protocolo de Internet versión**y, a continuación, haga clic en **propiedades**.  
  
    2.  Haga clic en el botón de radio junto a **usar la siguiente dirección IP**.  
  
2.  Escriba un valor para el **dirección IP** campo desde el intervalo de IP privada direcciones identificados en el "RFC 1918, asignación de direcciones para direcciones IP privadas" en [http://go.microsoft.com/fwlink/?LinkID=31904](http://go.microsoft.com/fwlink/?LinkID=31904).  
  
3.  Tome nota de la dirección IP que especificó; debe asociar el nombre NetBIOS del equipo en una entrada de archivo de HOSTS más adelante en este valor.  
  
4.  Escriba un valor adecuado para la **máscara de subred** campo.  
  
    > [!NOTE]  
    >  Windows debe rellenar el **máscara de subred** campo con un valor adecuado en función del valor que ha introducido en el **dirección IP** campo.  
  
5.  Deje el **puerta de enlace predeterminada** haga clic en de campo en blanco, **Aceptar**y, a continuación, haga clic en **cerrar**.  
  
6.  Después de configurar cada máquina virtual con una única dirección IP privada, actualice el archivo de HOSTS en cada máquina virtual con el nombre de NetBIOS de las otras máquinas virtuales ejecutando en el equipo de host de Hyper-V y la dirección IP. El archivo de HOSTS actualizado debe guardarse en la carpeta %systemroot%\drivers\etc\ en cada máquina virtual.  
  
    > [!NOTE]  
    >  Dado que de forma predeterminada, Windows comprueba el archivo de HOSTS local para resolver nombres NetBIOS, al actualizar el archivo de HOSTS en cada máquina virtual con las direcciones IP privadas únicas de las otras máquinas virtuales, tráfico de red entre estos máquina ahora se enrutará a través la red privada virtual.  
  
### <a name="disable-tcp-offloading-for-the-virtual-machine-network-cards"></a>Deshabilitar la descarga de TCP para las tarjetas de red de máquina Virtual  
 Editar el registro como se describe en el tema MSDN "Mediante los valores del registro para habilitar y deshabilitar la tarea Offloading (NDIS 5.1)" en [http://go.microsoft.com/fwlink/?LinkId=147619](http://go.microsoft.com/fwlink/?LinkId=147619) para deshabilitar la descarga de TCP para las tarjetas de red en cada máquina virtual.  
  
> [!IMPORTANT]  
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base "Descripción del registro de Microsoft Windows" en [http://go.microsoft.com/fwlink/?LinkId=62729](http://go.microsoft.com/fwlink/?LinkId=62729).  
  
## <a name="general-guidelines-for-improving-network-performance"></a>Directrices generales para mejorar el rendimiento de red  
 Las recomendaciones siguientes pueden utilizarse para aumentar el rendimiento de red:  
  
### <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a>Agregar tarjetas de red adicionales a los equipos en el entorno de BizTalk Server  
 Basta con agregar como unidades de disco duro adicionales pueden mejorar el rendimiento de disco, agregar tarjetas de red adicionales pueden mejorar el rendimiento de la red. Si las tarjetas de red en los equipos de su entorno de BizTalk Server están saturadas y la tarjeta es un cuello de botella, considere la posibilidad de agregar uno o más tarjetas de red adicionales para mejorar el rendimiento.  
  
### <a name="implement-network-segmentation"></a>Implementar la segmentación de la red  
 Siga las recomendaciones de la **subredes** sección de las notas del producto "Optimización de base de datos de BizTalk Server" en [http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578).  
  
### <a name="where-possible-replace-hubs-with-switches"></a>Siempre que sea posible, reemplace los concentradores con modificadores  
 Conmutadores contienen lógica para enrutar directamente el tráfico entre el origen y destino, mientras que los centros de usan un modelo para enrutar el tráfico de difusión. Por lo tanto, los conmutadores son más eficaces y ofrecen un mejor rendimiento.  
  
### <a name="remove-unnecessary-network-protocols"></a>Quitar protocolos de red innecesarios  
 Equipos con Windows Server a veces tengan más servicios de red y protocolos instalados que son realmente necesarios. Cada protocolo, servicio o cliente de red adicional coloca más sobrecarga de recursos del sistema.  
  
 Además, cada protocolo instalado genera tráfico de red. Mediante la eliminación de protocolos, servicios y clientes de red innecesarias, los recursos del sistema se ponen a disposición de otros procesos, se evita el exceso de tráfico de red y el número de enlaces de red que se debe negociar se reduce al mínimo.  
  
 Para ver los clientes de red instalados actualmente, protocolos y servicios, siga estos pasos:  
  
1.  Haga clic en **iniciar**, seleccione **configuración**y, a continuación, haga clic en **el Panel de Control**.  
  
2.  Haga doble clic en **las conexiones de red** para mostrar las conexiones de red en el equipo.  
  
3.  Haga clic en **conexión de área Local** (o la entrada para la conexión de red) y, a continuación, haga clic en **propiedades** para mostrar el cuadro de diálogo de propiedades para la conexión de red.  
  
4.  Para quitar un elemento innecesario, selecciónelo y haga clic en **desinstalar**. Para deshabilitar un elemento, simplemente desactive la casilla asociada al elemento.  
  
 Si no está seguro acerca de los efectos de la desinstalación de un elemento para la conexión, deshabilite el elemento en lugar de desinstalarlo. Deshabilitar elementos permite determinar qué servicios, protocolos y los clientes son realmente necesarios en un sistema. Cuando se ha determinado que deshabilitar un elemento no tiene ningún efecto adverso en el servidor, a continuación, se puede desinstalar el elemento.  
  
 En muchos casos, solo los tres componentes siguientes son necesarios para la operación en una red TCP/IP según estándar:  
  
-   Cliente para redes Microsoft  
  
-   Compartir archivos e impresoras para redes Microsoft  
  
-   Protocolo de Internet (TCP/IP)  
  
### <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a>Controladores de adaptadores de red en todos los equipos en el entorno de BizTalk Server deben optimizarse para rendimiento  
  
> [!IMPORTANT]  
>  Antes de aplicar la optimización en controladores de adaptador de red, siempre que instale a los controladores más recientes de dispositivo de adaptador de red para las tarjetas de red en el entorno.  
  
 Ajustar los controladores de dispositivo del adaptador de red para maximizar la cantidad de memoria disponible para el almacenamiento en búfer en paquetes tanto entrante como saliente. También maximizar recuentos de búfer, especialmente búferes de transmisión y búferes de unión. Los valores predeterminados para estos parámetros y si se proporcionan incluso, varían entre los fabricantes y las versiones del controlador. El objetivo es maximizar el trabajo realizado por el hardware del adaptador de red y para permitir que el mayor espacio de búfer para las operaciones de red mitigar ráfagas de tráfico de red y la congestión asociada.  
  
> [!NOTE]  
>  Pasos para optimizar los controladores de adaptador de red varían según el fabricante.  
  
 Siga estos pasos para tener acceso a la configuración de los adaptadores de red en[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]:  
  
1.  Haga clic en **iniciar**,, y, a continuación, haga clic en **el Panel de Control**.  
  
2.  Haga clic en **red e Internet**y, a continuación, haga clic en **centro de redes y recursos compartidos**.  
  
3.  Haga clic en **cambiar configuración del adaptador**, haga clic en **conexión de área Local** (o el nombre de la conexión de red) y, a continuación, haga clic en **propiedades**.  
  
4.  En el **General** , haga clic en **configurar**.  
  
5.  Haga clic en el **avanzadas** ficha a las propiedades de acceso que se pueden configurar para el adaptador de red.  
  
 Las siguientes propiedades se deben configurar para cada adaptador de red en el entorno de BizTalk Server:  
  
> [!NOTE]  
>  Aplicar esta configuración para cada adaptador de red físico, incluidos los adaptadores de red individuales dentro de un conjunto en equipo de adaptadores de red que están configurados para la agregación, equilibrio de carga y tolerancia a errores. Con algunos programas de software de formación de equipos, deberá aplicar esta configuración en el equipo también. Tenga en cuenta que algunos adaptadores de red son autoajustables y no podrán usar la opción para configurar los parámetros manualmente.  
  
-   **Opción de energía** : configurar el controlador de adaptador de red para impedir que la funcionalidad de administración de energía al desactivar el adaptador de red para ahorrar energía. Esta funcionalidad puede ser útil para los equipos cliente, pero debe rara vez, si alguna vez, puede usar en un equipo de BizTalk Server o SQL Server.  
  
-   **Fija la velocidad y dúplex (no utilice AUTO)** -es muy importante que la velocidad de la red, dúplex y parámetros de control de flujo se establecen de acuerdo con la configuración en el conmutador al que está conectados. Esto mitigará la aparición de "auto-sincronización periódica" lo que puede tardar temporalmente las conexiones fuera de línea.  
  
-   **Max fusionar búferes** -registros de mapa son recursos del sistema utilizados para convertir direcciones físicas para direcciones virtuales para los adaptadores de red que admiten el control por bus. Fusionar los búferes están disponibles para el controlador de red si el controlador se ejecuta fuera de los registros de mapa. Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto podría tener un negativo impacto como búferes de unión consumen memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Descriptores de transmisión y envío de Max y búferes de envío** -esta configuración especifica cuántos asigna el controlador para su uso por la interfaz de red de búferes de control de transmisión. Esto refleja directamente el número de paquetes pendientes que el controlador puede tener en su cola de "envío". Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto puede tener un impacto negativo como búferes de envío consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Búferes de recepción de max** -esta configuración especifica la cantidad de búfer de memoria utilizado por el controlador de interfaz de red cuando se copian datos a la memoria de protocolo. Normalmente se establece de forma predeterminada en un valor relativamente bajo. Establezca este valor tan alto como sea posible para un rendimiento máximo. En los servidores con una memoria física limitada, esto podría tener un negativo impacto como búferes de recepción consume memoria del sistema. En la mayoría de los sistemas sin embargo, el valor máximo puede aplicarse sin reducir significativamente la memoria disponible.  
  
-   **Todas las opciones de descarga en** : en casi todos los casos, el rendimiento mejora al habilitar características de descarga de interfaz de red. Algunos adaptadores de red proporcionan parámetros separados para habilitar o deshabilitar la descarga para enviar y recibir tráfico. Descargar las tareas de la CPU para el adaptador de red puede ayudar a un menor uso de CPU en el servidor que mejorará el rendimiento general del sistema. El transporte de Microsoft TCP/IP puede descargar una o varias de las siguientes tareas para un adaptador de red que tenga las capacidades adecuadas:  
  
    -   **Tareas de suma de comprobación** : transporte del TCP/IP puede descargar el cálculo y validación de las sumas de comprobación IP y TCP para envía y recibe al adaptador de red, habilite esta opción si el controlador de adaptador de red proporciona esta capacidad.  
  
    -   **Las tareas de seguridad IP** -transporte del TCP/IP puede descargar el cálculo y la validación de las sumas de comprobación cifrado para los encabezados de autenticación (AH) y encapsuladora (ESP) de cargas de seguridad para el adaptador de red. El transporte de TCP/IP también puede descargar el cifrado y descifrado de cargas de ESP al adaptador de red. Habilitar estas opciones si el controlador de adaptador de red proporciona esta capacidad.  
  
    -   **Segmentación de los paquetes TCP grandes** -transporte del TCP/IP es compatible con la descarga de envío grande (LSO). Con LSO, el transporte de TCP/IP puede descargar la segmentación de los paquetes TCP grandes.  
  
    -   **Descarga de la pila** : la pila de toda la red se pueden descargar en un adaptador de red que tenga las capacidades adecuadas. Habilite esta opción si el controlador de adaptador de red proporciona esta capacidad.  
  
-   **Wake On LAN deshabilitado (a menos que se usan)** : configurar el controlador de adaptador de red para deshabilitar la funcionalidad de lan wake-on. Esta funcionalidad puede ser útil para los equipos cliente, pero rara vez si alguna vez se debe utilizar en un equipo de BizTalk Server o SQL Server.  
  
 Para obtener más información acerca del ajuste de los adaptadores de red para el rendimiento, consulte el **configuración de dispositivo de red** sección de las notas del producto "Optimización de base de datos de BizTalk Server" en [http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578).
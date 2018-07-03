---
title: Solucionar problemas con MSDTC | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f39cde52-da8f-4cc1-bdc5-e4b828891a79
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95776b7b03cc1b6bca08622d126153cb22efc317
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987725"
---
# <a name="troubleshooting-problems-with-msdtc"></a>Solucionar problemas con MSDTC
La mayoría de las operaciones en tiempo de ejecución de BizTalk Server necesitan ser compatibles con Microsoft Distributed Transaction Coordinator (MSDTC) para asegurar que las operaciones coincidan con respecto a las transacciones. Si la compatibilidad de la transacción MSDTC no está disponible, las operaciones en tiempo de ejecución de BizTalk Server asociadas no pueden continuar. Los componentes de BizTalk que están comúnmente afectados cuando no está configurada correctamente la compatibilidad de la transacción MSDTC incluyen (aunque no son los únicos) el servicio de inicio de sesión único, las instancias de host de BizTalk y cualquier instancia de SQL Server que esté conectada por BizTalk Server. Esta sección contiene información que describe errores relativos a MSDTC y los pasos que se pueden realizar para diagnosticar y resolver problemas con MSDTC.  
  
## <a name="errors-that-can-occur-if-msdtc-transaction-support-is-not-configured-correctly"></a>Errores que se pueden producir si no está configurada correctamente la compatibilidad de la transacción MSDTC  
 Se pueden producir errores similares a los siguientes en BizTalk Server si no está configurada correctamente la compatibilidad de la transacción MSDTC en los equipos en un entorno de BizTalk:  
  
- "Un problema en el Coordinador de transacciones distribuidas de Microsoft impidió que se efectuara la conexión con la base de datos de configuración. El administrador de transacción ha deshabilitado su soporte para transacciones de red o remotas.  
  
- "Un problema en el Coordinador de transacciones distribuidas de Microsoft impidió que se efectuara la conexión con la base de datos de configuración. La transacción ya se ha llevado a cabo o se ha cancelado implícita o explícitamente".  
  
- "Código de error: 0x8004d00a, No se puede dar de alta la nueva transacción en el coordinador de transacciones especificado".  
  
- "No se pudieron recuperar los datos de tipo de transporte para la ubicación de recepción 'MySample ReceiveLocation' del almacén de configuración. Error en el servidor de inicio de sesión principal 'MyServer'. "El servidor de RPC no está disponible".  
  
- "Código de error: 0x8004d025, El administrador de transacción asociado deshabilitó la compatibilidad con las transacciones de red o remotas".  
  
- "Código de error: 0xc0002a24, No se pudo importar una transacción DTC. Compruebe que MSDTC está correctamente configurado para funcionamiento remoto".  
  
- "0x8004d01c  
  
   [0x1705] Error al crear el elemento de trabajo interno.  
  
   Asegúrese de que el servidor SQL Server se esté ejecutando.”  
  
  Para resolver los errores de configuración de MSDTC, siga los pasos que se indican a continuación.  
  
## <a name="ensure-netbios-name-resolution-between-the-biztalk-server-and-remote-servers-is-successful"></a>Asegurarse de que la resolución de nombre NetBIOS entre el servidor BizTalk Server y los servidores remotos es correcta  
 Las transacciones MSDTC correctas entre equipos necesitan que el equipo cliente pueda resolver el nombre NetBIOS del equipo servidor en la dirección IP correcta y el equipo servidor pueda resolver el nombre NetBIOS del equipo cliente en la dirección IP correcta. Para comprobar que la resolución de nombre NetBIOS funciona en ambas direcciones (cliente a servidor y servidor a cliente), siga estos pasos:  
  
> [!NOTE]
>  El nombre NetBIOS se conoce también comúnmente como el **red** nombre.  
  
1. Determine el nombre NetBIOS de cada equipo:  
  
   1.  Haga clic en **Mi PC** para mostrar el **las propiedades del sistema** cuadro de diálogo y haga clic en el **nombre_equipo** pestaña para ver el **nombre completo del equipo**asignada al equipo.  
  
   2.  El nombre NetBIOS es la primera parte del nombre designado como el **nombre completo del equipo** así, por ejemplo si el **nombre completo del equipo** se muestra como myserver.company.domain.com, a continuación, el nombre de NetBIOS de la es equipo **myserver**.  
  
2. Determine la dirección IP o direcciones que se han asociado a cada equipo:  
  
   1.  Inicie un símbolo del sistema en el equipo cliente, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ipconfig /all  
       ```  
  
   2.  La dirección IP o direcciones asociadas al equipo cliente aparecen en la ventana del símbolo del sistema.  
  
   3.  Inicie un símbolo del sistema en el equipo servidor, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ipconfig /all  
       ```  
  
   4.  La dirección IP o direcciones asociadas al equipo servidor aparecen en la ventana del símbolo del sistema.  
  
3. Compruebe que el nombre NetBIOS de cada equipo se resuelve en una de las direcciones IP asociadas al equipo:  
  
   1.  Inicie un símbolo del sistema en el equipo cliente, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ping <NetBIOS name of server computer>  
       ```  
  
        Los resultados del comando ping deben devolver una dirección IP asociada al equipo servidor.  
  
   2.  Inicie un símbolo del sistema en el equipo servidor, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ping <NetBIOS name of client computer>  
       ```  
  
        Los resultados del comando ping deben devolver una dirección IP asociada al equipo cliente.  
  
4. Compruebe que la búsqueda inversa de nombre de la dirección IP asociada con el nombre NetBIOS de cada equipo se resuelve en el nombre de equipo correcto:  
  
   1.  Inicie un símbolo del sistema en el equipo cliente, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ping -a <IP Address associated with client computer NetBIOS name>  
       ```  
  
        Los resultados del comando ping deberían devolver un nombre NetBIOS o nombre de dominio completo que corresponda al nombre NetBIOS que se usó en el paso 3a. Si el nombre devuelto no coincide o corresponde con el nombre NetBIOS usado en el paso 3a, la búsqueda inversa de dirección IP producirá un error que puede hacer que las transacciones MSDTC produzcan un error.  
  
   2.  Inicie un símbolo del sistema en el equipo servidor, escriba el siguiente comando y, a continuación, presione ENTRAR:  
  
       ```  
       ping -a <IP Address associated with server computer NetBIOS name>  
       ```  
  
        Los resultados del comando ping deberían devolver un nombre NetBIOS o nombre de dominio completo que corresponda al nombre NetBIOS que se usó en el paso 3b. Si el nombre devuelto no coincide o corresponde con el nombre NetBIOS usado en el paso 3b, la búsqueda inversa de dirección IP producirá un error que puede hacer que las transacciones MSDTC produzcan un error.  
  
   Si la resolución de nombre NetBIOS no es correcta en ninguna dirección o la búsqueda inversa de nombre genera un error, cree las entradas adecuadas en el servidor DNS, el servidor de nombre NetBIOS, el archivo HOSTS o LMHOSTS para solucionar el problema.  
  
> [!NOTE]
>  El método de resolución de nombre utilizado por el equipo cambia según el tipo de nodo NetBIOS del equipo. Para obtener más información acerca de los tipos de nodo NetBIOS, vea [resolución de nombres NetBIOS](http://go.microsoft.com/fwlink/?LinkId=201638).  
  
## <a name="ensure-that-a-firewall-between-the-biztalk-server-and-remote-servers-is-not-blocking-ports-required-for-rpc-dynamic-port-allocation"></a>Asegurarse de que un servidor de seguridad entre el servidor BizTalk Server y los servidores remotos no esté bloqueando puertos necesarios para la asignación de puerto dinámico RPC  
 La funcionalidad MSDTC a través de la red depende de la funcionalidad RPC a través de la red. La funcionalidad RPC a través de un servidor de seguridad necesita que determinados puertos estén abiertos para contener la asignación de puerto dinámico RPC. Si existe un firewall entre el servidor BizTalk Server y los servidores remotos, siga los pasos de [cómo configurar la asignación de puertos dinámicos RPC para trabajar con firewalls](http://go.microsoft.com/fwlink/?LinkId=66831) para dar cabida a la asignación de puertos dinámicos de RPC.  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options"></a>Definir las opciones de configuración de seguridad de MSDTC  
 Windows proporciona mejoras de seguridad que controlan cómo MSDTC accede a través de una red. Al modificar los valores de seguridad de MSDTC, podrá controlar cómo MSDTC se comunica con equipos remotos a través de la red. En esta tabla se enumeran los valores recomendados para las opciones que están disponibles al configurar los valores de seguridad de MSDTC:  
  
|Opción de configuración|Valor predeterminado|Valor recomendado|  
|--------------------------|-------------------|-----------------------|  
|Acceso de DTC a la red|Deshabilitado|Habilitado|  
|**Cliente y administración**|||  
|Permitir clientes remotos|Deshabilitado|Deshabilitado|  
|Permitir administración remota|Deshabilitado|Deshabilitado|  
|**Comunicación del Administrador de transacciones**|||  
|Permitir entrantes|Deshabilitado|Habilitado|  
|Permitir salientes|Deshabilitado|Habilitado|  
|Se requiere autenticación mutua|Habilitado|Está habilitada si todas las máquinas remotas ejecutan Windows Server 2003 SP1 o Windows XP SP2 o versiones posteriores y tienen configurada la opción “Se requiere autenticación mutua”.|  
|Se requiere autenticación de llamada entrante|Deshabilitado|Habilitada si se ejecuta MSDTC en el clúster.|  
|No se requiere autenticación|Deshabilitado|Habilitada si los equipos remotos disponen de una versión anterior a Windows Server 2003 SP1 o anterior a Windows XP SP2.|  
|Habilitar TIP|Deshabilitado|Habilitada si se ejecuta el Portal de BAM.|  
|Habilitar transacciones XA|Deshabilitado|Habilitada si se comunica con un sistema transaccional basado en XA, por ejemplo, al comunicarse con IBM WebSphere MQ a través del adaptador de MQSeries.|  
  
 Tras aplicar estos cambios, se reiniciará el servicio MSDTC.  
  
 Para obtener acceso a las opciones de configuración de seguridad de MSDTC, siga los pasos siguientes:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo **dcomcnfg** para iniciar el **servicios de componentes**consola de administración.  
  
2.  Haga clic para expandir **servicios de componentes** y haga clic para expandir **equipos**.  
  
3.  Haga clic para expandir **Mi PC**, haga clic para expandir **Coordinador de transacciones distribuidas**, haga clic en **DTC Local**y haga clic en **propiedades**.  
  
4.  Haga clic en el **seguridad** pestaña de la **propiedades de DTC Local** cuadro de diálogo.  
  
> [!NOTE]
>  En función de los cambios que haya efectuado, es posible que deba reiniciar el equipo para aplicarlos. Si tras aplicar los cambios y reiniciar el servicio MSDTC todavía experimenta algún problema, reinicie el equipo en el que se han hecho los cambios para garantizar que se hayan aplicado.  
  
 Si el **requiere autenticación mutua** o **requiere autenticación de llamada entrante** están habilitadas las opciones de configuración, a continuación, la cuenta del equipo cliente debe concederse el **Tener acceso a este equipo desde la red** derecho de usuario. Si la cuenta de equipo para un equipo cliente no se concede el **tener acceso a este equipo desde la red** derecho de usuario, o se incluye en el **denegar el acceso a este equipo desde la red** derecho de usuario y, a continuación, DTC se producirá un error de comunicación entre el equipo cliente y servidor.  
  
 El valor predeterminado es conceder al grupo todos los **tener acceso a este equipo desde la red** derecho de usuario. Por lo tanto, no será necesario cambiar este derecho de usuario a menos que se haya modificado la configuración predeterminada. Si el **No se requiere autenticación** está habilitada la opción de configuración de la **tener acceso a este equipo desde la red** derecho de usuario no es aplicable a la cuenta del equipo cliente.  
  
 Para cambiar los usuarios o grupos a los que se concede el permiso de usuario "Tener acceso a este equipo desde la red", realice los siguientes pasos.  
  
1. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **Gpedit.msc**y, a continuación, haga clic en **Aceptar**.  
  
2. Expanda los siguientes elementos en la lista Directiva de equipo local:  
  
   -   Configuración del equipo  
  
   -   Configuración de Windows  
  
   -   Configuración de seguridad  
  
   -   Directivas locales  
  
3. Haga clic en **asignación de derechos de usuario**.  
  
4. Haga doble clic en **tener acceso a este equipo desde la red**y, a continuación, haga clic en **Agregar usuario o grupo**.  
  
5. Haga clic en **tipos de objeto**, seleccione **equipos** y haga clic en **Aceptar**.  
  
6. Agregue el nombre de equipo o el nombre del grupo en el **escriba los nombres de objeto para seleccionar** área.  
  
7. Haga clic en **comprobar nombres** para comprobar la entrada.  
  
8. Haga clic en **Aceptar** dos veces.  
  
   Para cambiar los usuarios o grupos que se incluyen en el **denegar el acceso a este equipo desde la red** derecho de usuario, siga estos pasos:  
  
9. Expanda los siguientes elementos en la lista Directiva de equipo local:  
  
   -   Configuración del equipo  
  
   -   Configuración de Windows  
  
   -   Configuración de seguridad  
  
   -   Directivas locales  
  
10. Haga clic en **asignación de derechos de usuario**.  
  
11. Haga doble clic en **denegar el acceso a este equipo desde la red**y, a continuación, haga clic para seleccionar el nombre de equipo o grupo que desea quitar este derecho de usuario.  
  
12. Haga clic en **quitar** y, a continuación, haga clic en **Aceptar**.  
  
## <a name="set-the-appropriate-values-for-the-enableauthepresolution-and-restrictremoteclients-options"></a>Definir los valores adecuados para las opciones EnableAuthEpResolution y RestrictRemoteClients  
 Windows requiere llamadas autenticadas a la interfaz de RPC para mejorar la seguridad. Esta funcionalidad es configurable a través de la **EnableAuthEpResolution** y **RestrictRemoteClients** claves del registro. Siga estos pasos para garantizar que los equipos remotos puedan obtener acceso a la interfaz de RPC:  
  
> [!WARNING]
>  El uso incorrecto del Editor del Registro podría ocasionar problemas que hicieran necesaria una reinstalación del sistema operativo. Utilice el Editor del Registro bajo su propia responsabilidad. Para obtener más información acerca de cómo realizar copias de seguridad, restaurar y modificar el registro, consulte el artículo de Microsoft Knowledge Base "Descripción del registro de Microsoft Windows" en [descripción del registro de Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=62729).  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit.exe**y, a continuación, haga clic en **Aceptar** para iniciar el Editor del registro.  
  
     Vaya a **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows NT**  
  
2.  En el **RPC** clave, cree las siguientes entradas DWORD con los valores indicados. Si el **RPC** clave no existe, a continuación, se debe crear.  
  
    |Entrada DWORD|Valor predeterminado|Valor recomendado|  
    |-----------------|-------------------|-----------------------|  
    |EnableAuthEpResolution|0 (deshabilitada)|1|  
    |RestrictRemoteClients|1 (habilitada)|0|  
  
3.  Cierre el Editor del registro.  
  
4.  Reinicie el servicio MSDTC.  
  
> [!NOTE]
>  En función de los cambios que haya efectuado, es posible que deba reiniciar el equipo para aplicarlos. Si tras aplicar los cambios y reiniciar el servicio MSDTC todavía experimenta algún problema, reinicie el equipo en el que se han hecho los cambios para garantizar que se hayan aplicado.  
  
## <a name="if-windows-firewall-is-running-add-an-exception-for-the-msdtc-service"></a>Si se está ejecutando Firewall de Windows, agregue una excepción para el servicio MSDTC  
 El servicio Firewall de Windows puede bloquear las comunicaciones MSDTC entre equipos. Para garantizar que no se bloqueen las comunicaciones MSDTC entre equipos, agregue msdtc.exe a la lista de excepciones de Firewall de Windows, si se está ejecutando el servicio Firewall de Windows.  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **firewall.cpl**y, a continuación, haga clic en **Aceptar** para mostrar el **deFirewalldeWindows** cuadro de diálogo.  
  
2.  Haga clic en **permitir un programa a través del Firewall de Windows** para mostrar el **configuración de Firewall de Windows** cuadro de diálogo.  
  
3.  Haga clic en el **excepciones** pestaña de la **configuración de Firewall de Windows** cuadro de diálogo.  
  
4.  Haga clic en **Agregar programa** para mostrar el **agregar un programa** cuadro de diálogo.  
  
5.  Haga clic en **examinar** y vaya a *% system32%* \msdtc.exe.  
  
    > [!NOTE]
    >  Abra un símbolo del sistema, escriba **echo % system32%** y presione **ENTRAR** para determinar la ubicación del directorio \System32 en este equipo.  
  
6.  Haga clic para seleccionar **msdtc.exe** y haga clic en **abierto**.  
  
7.  Haga clic en **Cambiar ámbito** para especificar el conjunto de equipos para que MSDTC se deben permitir las comunicaciones y haga clic en **Aceptar**.  
  
8.  Haga clic en **Aceptar** en el **agregar un programa** cuadro de diálogo y haga clic en **Aceptar** en el **configuración de Firewall de Windows** cuadro de diálogo.  
  
9. Cerrar la **Windows Firewall** cuadro de diálogo.  
  
10. Detenga y reinicie el servicio del Coordinador de transacciones distribuidas.  
  
    -   Abra un símbolo del sistema, escriba **net stop msdtc** y presione **ENTRAR**.  
  
    -   Después de detener el servicio Coordinador de transacciones distribuidas, escriba **del comando net start msdtc** y presione **ENTRAR**.  
  
## <a name="use-dtctester-or-dtcping-to-verify-msdtc-functionality-over-the-network"></a>Utilizar DTCTester o DTCPing para comprobar la funcionalidad MSDTC a través de la red  
 Utilice la utilidad DTCTester para comprobar la compatibilidad con transacciones entre dos equipos, si SQL Server se ha instalado en uno de los equipos. La utilidad DTCTester utiliza ODBC para comprobar la compatibilidad con transacciones frente a una base de datos de SQL Server. Para obtener más información acerca de DTCTester, vea [cómo utilizar la herramienta DTCTester](http://go.microsoft.com/fwlink/?LinkId=66232).  
  
 Utilice DTCPing para comprobar la compatibilidad con transacciones entre dos equipos, si SQL Server no se ha instalado en ninguno de ellos. La herramienta DTCPing debe ejecutarse tanto en el equipo cliente como en el equipo servidor y se trata de una buena alternativa en la utilidad DTCTester cuando SQL Server no se ha instalado en ningún equipo. Para obtener más información acerca de DTCPing, vea [cómo solucionar problemas de firewall de MS DTC](http://go.microsoft.com/fwlink/?LinkId=61915).  
  
> [!IMPORTANT]
>  Si DTCPing devuelve la advertencia que "Advertencia: los valores de CID para ambos equipos de prueba son los mismos", a continuación, siga los pasos descritos en la sección **asegurarse de que MSDTC se asigna un valor de CID único** para dar cabida a la funcionalidad correcta de MSDTC entre las máquinas de prueba.  
  
## <a name="ensure-that-msdtc-is-assigned-a-unique-cid-value"></a>Asegurarse de que se asigne un valor de CID único a MSDTC  
 La característica MSDTC del sistema operativo Windows requiere valores de CID únicos para garantizar que la funcionalidad MSDTC funcione correctamente entre equipos. Las imágenes duplicadas de las instalaciones de Windows en el disco deben tener valores de CID únicos; de lo contrario, es posible que MSDTC no funcione correctamente. Esto puede suceder si se utilizan discos duros virtuales para implementar un sistema operativo en un equipo virtual.  
  
 Para determinar si son únicos los valores de CID de MSDTC de los equipos que ejecutan el sistema operativo Windows, compruebe los valores de las entradas en la clave del Registro HKEY_CLASSES_ROOT\CID en ambos equipos. Si estos valores no son únicos para cada equipo, a continuación, siga los pasos descritos en la sección **considere la posibilidad de volver a instalar el servicio Coordinador de transacciones distribuidas si otros pasos de solución de problemas no son correctas** para volver a instalar MSDTC en uno los equipos, que, a continuación, generará valores únicos de CID de MSDTC para ese equipo y adaptarse a las operaciones de MSDTC adecuadas.  
  
## <a name="error-new-transaction-cannot-enlist-in-the-specified-transaction-coordinator-0x8004d00a-occurs-if-the-msdtc-connection-between-a-client-computer-and-a-server-computer-is-closed"></a>Se produce el error “No se puede dar de alta una nueva transacción en el coordinador de transacciones especificado (0x8004d00a)” si la conexión de MSDTC entre un equipo cliente y un equipo servidor está cerrada  
 En determinados escenarios, es posible que se cierra una conexión MSDTC existente entre un cliente y servidor e intenta usar esta conexión dará como resultado el siguiente mensaje de error:  
No se puede dar de alta la nueva transacción en el Coordinador de transacciones especificado (0x8004d00a)  
Para obtener más información, consulte [recibe un mensaje de Error cuando intenta iniciar una transacción en MS DTC: "no se puede dar de alta la nueva transacción en el Coordinador de transacciones especificado"](http://support.microsoft.com/kb/922430).  
  
## <a name="consider-reinstalling-the-distributed-transaction-coordinator-service-if-other-troubleshooting-steps-are-not-successful"></a>Considerar la posibilidad de volver a instalar el servicio del Coordinador de transacciones distribuidas si otros pasos para la solución de problemas no logran resolverlo  
 Si otros intentos de solucionar problemas con MSDTC no son satisfactorios considere la posibilidad de desinstalar y volver a instalar MSDTC. Siga estos pasos para desinstalar y volver a instalar MSDTC:  
  
1.  Abra un símbolo del sistema como administrador.  
  
2.  En el símbolo del sistema, escriba lo siguiente para desinstalar el servicio Coordinador de transacciones distribuidas:  
    `msdtc -uninstall`  
  
3.  En el símbolo del sistema, escriba lo siguiente para instalar el servicio Coordinador de transacciones distribuidas:  
    `msdtc –install`  
  
> [!IMPORTANT]
>  Volver a instalar MSDTC puede cambiar el comportamiento predeterminado del servicio del coordinador de transacciones distribuidas. Siga estos pasos después de volver a instalar MSDTC para garantizar que el servicio del Coordinador de transacciones distribuidas funciona correctamente:  
> 
> - Volver a instalar MSDTC puede restablecer las opciones de configuración de seguridad de MSDTC a los valores predeterminados. Compruebe que las opciones de configuración de seguridad de MSDTC estén establecidas en los valores apropiados después de volver a instalar MSDTC.  
>   -   Volver a instalar MSDTC puede cambiar el **tipo de inicio** valor para el servicio Coordinador de transacciones distribuidas. Compruebe que la **tipo de inicio** valor para el servicio Coordinador de transacciones distribuidas se establece en **automática** después de volver a instalar MSDTC.  
>   -   Volver a instalar MSDTC puede requerir un reinicio del equipo. Para garantizar que el servicio del Coordinador de transacciones distribuidas funciona correctamente, reinicie el equipo después de volver a instalar MSDTC.  
  
## <a name="see-also"></a>Vea también  
 [Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Solución de problemas de un clúster de Windows Server](../core/troubleshooting-a-windows-server-cluster.md)
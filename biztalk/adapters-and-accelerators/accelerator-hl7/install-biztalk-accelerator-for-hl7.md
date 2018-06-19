---
title: Instalar el Acelerador de BizTalk para HL7 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52347742-f858-47bb-bc73-1a6095ea9e8e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ad01c0b3966985efdceea421de85778266a294c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205108"
---
# <a name="install-biztalk-accelerator-for-hl7"></a>Instalar el Acelerador de BizTalk para HL7

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y de software

Los requisitos mínimos de hardware y software son los mismos que [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. 

|  |Requisitos de BizTalk  |Requisitos de SQL y el sistema operativo |  
|---------|---------|--------- | 
| [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016) | **Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx) |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) |**Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx)  |

> [!TIP]
> Los requisitos de hardware enumerados son los mínimos. Cada entorno es diferente y es muy probable que el suyo tenga más requisitos. Vea [recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)

## <a name="install-hl7"></a>Instalar HL7

### <a name="before-you-begin"></a>Antes de empezar

* Los archivos de instalación del Acelerador de HL7 están en `BizTalk Server <version>\BizTalk Accelerators` en el [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] ISO, ubicación de descarga, recurso compartido de red, o, donde descargó el [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] programa.
* El usuario de instalación y configuración de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] debe ser un miembro del grupo Administradores de BizTalk y un miembro del grupo Administradores en el servidor SQL Server donde el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] se almacenan los datos.
* El equipo y el usuario que inició sesión deben tener acceso al controlador de dominio principal (PDC). Si el programa de instalación no puede acceder el PDC y, a continuación, la instalación produce un error y no continuará.  
* BizTalk Server debe tener los componentes básicos instalado y configurado, incluido un host de BizTalkServerApplication de 32 bits con estándar fuera del cuadro adaptadores, el inicio de sesión único empresarial (SSO), el grupo y en tiempo de ejecución.
* Leer la [problemas conocidos de instalación](../../adapters-and-accelerators/accelerator-hl7/installation-known-issues.md).
*  [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]está disponible en las ediciones Enterprise y Standard. La siguiente tabla muestra la compatibilidad entre las diferentes ediciones de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
    |Edición de[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] |Ediciones compatibles de[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]|  
    |---|---|  
    |Enterprise Edition|Enterprise Edition|  
    |Standard Edition|Enterprise o Standard Edition|  
    |Developer Edition|Enterprise Edition|  

### <a name="default-installation"></a>Instalación predeterminada

1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe** como administrador. 
  
    > [!TIP]
    >  A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] y versiones posteriores, el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] instalación incluye un paquete de instalación de 32 bits y un paquete de instalación de 64 bits.
    > 
    > En un equipo de 32 bits, instale únicamente el paquete de 32 bits. En un equipo de 64 bits, instale lo 32 bits **o** paquete de 64 bits. El paquete de 64 bits permite que el adaptador y las canalizaciones se ejecuten en modo de 32 bits y de 64 bits.  
  
2.  En la página de bienvenida, seleccione **siguiente**.  
  
3.  Acepte la **contrato de licencia**y, a continuación, seleccione **siguiente**.  
  
4.  Escriba el nombre de usuario y la organización y, a continuación, seleccione **siguiente**.  
  
5.  Seleccione el **típica** el programa de instalación y, a continuación, seleccione **siguiente**.  
  
6.  El **cuenta de servicio de registro** página proporciona automáticamente los siguientes grupos de los permisos de registro: 

  * Administradores de servidor BizTalk Server
  * Usuarios de aplicación de BizTalk
  * Operadores B2B de BizTalk Server
  * Operadores de servidor BizTalk Server

    Seleccione **Siguiente**. 

7. Revise el resumen y seleccione **siguiente**.  

8. Para el **carpeta de destino**, seleccione **siguiente** para usar la carpeta predeterminada. O bien, seleccione **cambio** para elegir otra carpeta de instalación. 

9. En **información de base de datos de registro**, escriba lo siguiente y, a continuación, seleccione **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre del servidor de base de datos**|El valor predeterminado es el nombre del servidor. <br/><br/>**Tenga en cuenta** el nombre del servidor es el nombre del equipo que reside la base de datos de BizTalkMgmtDb. No se puede cambiar este valor.|  
    |**Nombre de base de datos de HL7**|Escriba el nombre de la base de datos que contiene los datos para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución, o acepte la configuración predeterminada, que es **BTAHL7**. <br/><br/>**Tenga en cuenta** debe utilizar el carácter ANSI-ASCII establecer según los requisitos de base de datos; [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] no admite otros juegos de caracteres.|  
    | **Probar conexión** | Seleccione esta opción para confirmar que tiene conectividad de SQL Server. |
  
    > [!NOTE]
    >  Si la base de datos seleccionada ya existe, aparece un cuadro de mensaje. Seleccione **Aceptar** para continuar.  
    
10. Seleccione **Instalar**.
  
11. Seleccione **finalizar** finalizada.  
  
    > [!TIP] 
    > Seleccione **iniciar Tutorial** para instalar el Tutorial de End-To-End. 
    
### <a name="custom-installation"></a>Instalación personalizada
1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe** como administrador. 
  
    > [!TIP]
    >  A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] y versiones posteriores, el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] instalación incluye un paquete de instalación de 32 bits y un paquete de instalación de 64 bits. 
    > 
    > En un equipo de 32 bits, instale únicamente el paquete de 32 bits. En un equipo de 64 bits, instale lo 32 bits **o** paquete de 64 bits. El paquete de 64 bits permite que el adaptador y las canalizaciones se ejecuten en modo de 32 bits y de 64 bits.  
  
2.  En la página de bienvenida, seleccione **siguiente**.  
  
3.  Acepte la **contrato de licencia**y, a continuación, seleccione **siguiente**.  
  
4.  Escriba su nombre de usuario y contraseña y, a continuación, seleccione **siguiente**.  
  
5. Seleccione **personalizado**y, a continuación, seleccione **siguiente**.  
  
6.  Seleccione las características que desea instalar y, a continuación, seleccione **siguiente**.  
  
    |Característica|Subcaracterística de características|Description|Instalación típica|Instalación personalizada|  
    |---|---|---|---|---|  
    |**Motor de**||Valida, procesa y enruta los mensajes.<br /><br /> Debe ser miembro del grupo Administradores de BizTalk Server para instalar esta característica.|✓|✓|  
    |**Motor de**|Componentes del motor|Procesos [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] planos, archivos y mensajes codificados en XML.|✓|✓|  
    |**Motor de**|Procesamiento por lotes saliente|Se crea y se enruta [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] documentos con formato de lote.|✓|✓|  
    |**Motor de**|Canalizaciones|Ejemplo de canalizaciones para crear su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.|✓|✓|  
    |**Adaptador**||Utilidades para habilitar las conexiones de extremo.|✓|✓|  
    |**Adaptador**|MLLP|Adaptador MLLP para habilitar las conexiones basadas en TCP/IP mediante [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] protocolo MLLP.|✓|✓|  
    |**Adaptador**|Herramienta de prueba MLLP|Probar herramienta que emula basado en MLLP enviar y recibir las aplicaciones cliente a través de conexiones basadas en TCP/IP.|||  
    |**Esquemas**||Selección de HL7 V2. Archivo sin formato X según los esquemas XSD.|✓|✓|  
    |**Artefactos**||Herramientas para trabajar con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos.||✓|  
    |**Artefactos**|Orquestación|Una orquestación de ejemplo que puede usar para crear su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.||✓|  
    |**Otros componentes**|Instancias de prueba|Prueba/muestra datos que se puede utilizar como punto de partida para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.|||  
    |**Otros componentes**|-|Otros componentes de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].|✓|✓|  
    |**Otros componentes**|Explorador de configuración|Aplicación que se usa para definir el registro en los almacenes de datos, configurar la validación específica de la entidad, la asignación de encabezado, el procesamiento por lotes y los requisitos de confirmación.|✓|✓|  
    |**Otros componentes**|SDK|Contiene utilidades para HL7 2. los esquemas XML, como los componentes y los artefactos necesitan para el Tutorial de extremo a extremo y la MLLP utilidades.|✓|✓|  
    |**Otros componentes**|Marco de registro|Componentes que admiten el registro de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] eventos.|✓|✓|  
    |**Otros componentes**|Proyecto de inicio|Complemento para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] que permite [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] desarrollo del proyecto.|✓|✓|  
  
7. En **cuenta de servicio de registro**, escriba lo siguiente y, a continuación, seleccione **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de cuenta**|Escriba el nombre de cuenta que desea usar para iniciar el servicio de registro.|  
    |**Contraseña**|Escriba la contraseña para esta cuenta.|  
    |**Dominio**|Escriba el nombre de dominio para esta cuenta.|  
  
8. Cuando se le pida **se ha concedido el nombre de cuenta de inicio de sesión como servicio derecho**, seleccione **Aceptar**.  
  
9. Revise el resumen y seleccione **siguiente**.  
  
10. Para el **carpeta de destino**, seleccione **siguiente** para usar la carpeta predeterminada. O bien, seleccione **cambio** para elegir otra carpeta de instalación.
  
11. En **información de base de datos de registro** página, escriba lo siguiente y, a continuación, seleccione **siguiente**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre del servidor de base de datos**|El valor predeterminado es el nombre del servidor. <br/><br/>**Tenga en cuenta** el nombre del servidor es el nombre del equipo que reside la base de datos de BizTalkMgmtDb. No se puede cambiar este valor.|  
    |**Nombre de base de datos de HL7**|Escriba el nombre de la base de datos que contiene los datos para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución, o acepte la configuración predeterminada; que es **BTAHL7**. <br/><br/> **Tenga en cuenta** debe utilizar el carácter ANSI-ASCII establecer según los requisitos de base de datos; [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] no admite otros juegos de caracteres.|  
  
12. Seleccione **Instalar**.  
  
15. Seleccione **finalizar** finalizada.  
  
    > [!TIP] 
    > Seleccione **iniciar Tutorial** para instalar el Tutorial de End-To-End.   
    
## <a name="next-steps"></a>Pasos siguientes
Paso a través de algunos tutoriales en [empezar a trabajar con el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md).
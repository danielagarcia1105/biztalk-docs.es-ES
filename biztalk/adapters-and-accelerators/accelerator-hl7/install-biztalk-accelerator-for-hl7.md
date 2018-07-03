---
title: Instalar el Acelerador de BizTalk para HL7 | Microsoft Docs
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
ms.openlocfilehash: 3d20e2fa78d921c160b8dfe6b96c79c1b15d353e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004997"
---
# <a name="install-biztalk-accelerator-for-hl7"></a>Instalar el Acelerador de BizTalk para HL7

## <a name="hardware-and-software-requirements"></a>Requisitos de hardware y de software

Los requisitos mínimos de hardware y software son los mismos como [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. 


|                                                                                                                                                                   |                                                                                Requisitos de BizTalk                                                                                 |                                                                                                                                                                                                                                                            Requisitos del sistema operativo y SQL                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                       [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]                                                        |             [Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016)             |                                      **Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2016](https://msdn.microsoft.com/library/ms143506(v=sql.130).aspx)<br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/server-basics)<br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)                                      |
| [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] <br/><br/> [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] 2013 | [Requisitos de hardware y software de BizTalk Server 2013 y 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md) | **Requisitos de hardware y software de SQL Server**: <br/>[SQL Server 2014](https://msdn.microsoft.com/library/ms143506(v=sql.120).aspx)<br/>[SQL Server 2012](https://msdn.microsoft.com/library/ms143506(v=sql.110).aspx)<br/>[SQL Server 2008 R2](https://msdn.microsoft.com/library/ms143506(v=sql.105).aspx)<br/><br/>**Requisitos de hardware de Windows Server**: <br/>[Windows Server 2012](https://technet.microsoft.com/library/jj134246.aspx)<br/>[Windows Server 2008 R2](https://technet.microsoft.com/library/dd379511(v=ws.10).aspx) |

> [!TIP]
> Los requisitos de hardware enumerados son los mínimos. Cada entorno es diferente y es muy probable que el suyo tenga más requisitos. Consulte [recomendaciones para instalar, ajustar el tamaño, implementar y mantener una solución de BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/666.recommendations-for-installing-sizing-deploying-and-maintaining-a-biztalk-server-solution.aspx)

## <a name="install-hl7"></a>Instalar HL7

### <a name="before-you-begin"></a>Antes de comenzar

* Los archivos de instalación del Acelerador HL7 están en `BizTalk Server <version>\BizTalk Accelerators` en el [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] ISO, ubicación de descarga, el recurso compartido de red, o donde descargó el [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] programa.
* El usuario de instalación y configuración [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] debe ser miembro del grupo Administradores de BizTalk y un miembro del grupo Administradores en el servidor SQL donde el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] se almacenan los datos.
* El equipo y el usuario que inició sesión deben tener acceso al controlador de dominio principal (PDC). Si el programa de instalación no puede acceder a lo PDC, a continuación, la instalación produce un error y no continuará.  
* BizTalk Server debe tener los componentes básicos instalado y configurado, incluido un host de BizTalkServerApplication de 32 bits con estándar de los adaptadores predefinidos, el inicio de sesión único empresarial (SSO), el grupo y en tiempo de ejecución.
* Leer el [problemas conocidos de instalación](../../adapters-and-accelerators/accelerator-hl7/installation-known-issues.md).
* [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] está disponible en las ediciones Enterprise y Standard. En la tabla siguiente se muestra la compatibilidad entre las diferentes ediciones de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  


  | Edición de[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  | Edición compatible de [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] |
  |-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
  |                                      Enterprise Edition                                       |                                     Enterprise Edition                                      |
  |                                       Standard Edition                                        |                               Edición Enterprise o Standard                                |
  |                                       Developer Edition                                       |                                     Enterprise Edition                                      |

### <a name="default-installation"></a>Instalación predeterminada

1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe** como administrador. 

   > [!TIP]
   >  A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] y versiones posteriores, el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] instalación incluye un paquete de instalación de 32 bits y un paquete de instalación de 64 bits.
   > 
   > En un equipo de 32 bits, instale únicamente el paquete de 32 bits. Instalación de 32 bits en un equipo de 64 bits, **o** paquete de 64 bits. El paquete de 64 bits permite que el adaptador y las canalizaciones se ejecuten en modo de 32 bits y de 64 bits.  

2. En la página de bienvenida, seleccione **siguiente**.  

3. Acepte el **contrato de licencia**y, a continuación, seleccione **siguiente**.  

4. Escriba el nombre de usuario y la organización y, a continuación, seleccione **siguiente**.  

5. Seleccione el **típica** de instalación y, a continuación, seleccione **siguiente**.  

6. El **cuenta de servicio de registro** página automáticamente proporciona los siguientes grupos de los permisos de registro: 

   * Administradores de servidor BizTalk Server
   * Usuarios de aplicación de BizTalk
   * Operadores B2B de BizTalk Server
   * Operadores de servidor BizTalk Server

   Seleccione **Siguiente**. 

7. Revise el resumen y seleccione **siguiente**.  

8. Para el **carpeta de destino**, seleccione **siguiente** para usar la carpeta predeterminada. O bien, seleccione **cambio** para elegir una carpeta de instalación diferente. 

9. En **información de base de datos de registro**, escriba lo siguiente y, a continuación, seleccione **siguiente**.  


   |         Use         |                                                                                                                                                                                                                   Para                                                                                                                                                                                                                   |
   |--------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Nombre del servidor de base de datos** |                                                                                                                             El valor predeterminado es el nombre del servidor. <br/><br/>**Tenga en cuenta** el nombre del servidor es el nombre del equipo que reside la base de datos BizTalkMgmtDb. No se puede cambiar este valor.                                                                                                                              |
   |  **Nombre de la base de datos de HL7**   | Escriba el nombre de la base de datos que contiene los datos para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución, o acepte la configuración predeterminada, que es **BTAHL7**. <br/><br/>**Tenga en cuenta** debe usar el carácter ANSI-ASCII establecer según los requisitos de base de datos; [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] no admite otros juegos de caracteres. |
   |   **Probar conexión**    |                                                                                                                                                                                              Seleccione esta opción para confirmar que tiene conectividad de SQL Server.                                                                                                                                                                                               |

    > [!NOTE]
    >  Si la base de datos que seleccionó ya existe, aparece un cuadro de mensaje. Seleccione **Aceptar** para continuar.  

10. Seleccione **Instalar**.

11. Seleccione **finalizar** finalizada.  

    > [!TIP] 
    > Seleccione **iniciar Tutorial** para instalar el Tutorial de extremo a otro. 

### <a name="custom-installation"></a>Instalación personalizada
1. Ejecute el [!INCLUDE[btaBTAHL7NoNumber_md](../../includes/btabtahl7nonumber-md.md)] (A4HL7) **setup.exe** como administrador. 

   > [!TIP]
   >  A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] y versiones posteriores, el [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] instalación incluye un paquete de instalación de 32 bits y un paquete de instalación de 64 bits. 
   > 
   > En un equipo de 32 bits, instale únicamente el paquete de 32 bits. Instalación de 32 bits en un equipo de 64 bits, **o** paquete de 64 bits. El paquete de 64 bits permite que el adaptador y las canalizaciones se ejecuten en modo de 32 bits y de 64 bits.  

2. En la página de bienvenida, seleccione **siguiente**.  

3. Acepte el **contrato de licencia**y, a continuación, seleccione **siguiente**.  

4. Escriba su nombre de usuario y contraseña y, a continuación, seleccione **siguiente**.  

5. Seleccione **personalizado**y, a continuación, seleccione **siguiente**.  

6. Seleccione las características que desea instalar y, a continuación, seleccione **siguiente**.  


   |       Característica        |      Subcaracterística       |                                                                                                   Descripción                                                                                                    | Instalación típica | Instalación personalizada |
   |----------------------|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|----------------|
   |      **Motor de**      |                        |                                 Valida, procesa y enruta los mensajes.<br /><br /> Debe ser miembro del grupo Administradores de BizTalk Server para instalar esta característica.                                  |        ✓        |       ✓        |
   |      **Motor de**      |   Componentes del motor    |                                      Procesos [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] planos, archivos y los mensajes codificados en XML.                                      |        ✓        |       ✓        |
   |      **Motor de**      |   Procesamiento por lotes saliente    |                                       Crea y distribuye [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] por lotes de documentos con formato.                                        |        ✓        |       ✓        |
   |      **Motor de**      |       Canalizaciones        |                                      Ejemplo canalizaciones para crear su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.                                       |        ✓        |       ✓        |
   |     **Adaptador**      |                        |                                                                                    Utilidades para habilitar las conexiones de punto de conexión.                                                                                    |        ✓        |       ✓        |
   |     **Adaptador**      |          MLLP          |                          Adaptador MLLP para habilitar las conexiones basadas en TCP/IP mediante [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] protocolo MLLP.                           |        ✓        |       ✓        |
   |     **Adaptador**      |     Herramienta de prueba de MLLP     |                                                   Probar la herramienta que emula el envío de MLLP y recibir las aplicaciones cliente a través de conexiones basadas en TCP/IP.                                                    |                 |                |
   |     **Esquemas**      |                        |                                                                                Selección de HL7 V2. Archivo plano X según los esquemas XSD.                                                                                |        ✓        |       ✓        |
   |    **Artefactos**     |                        |                                             Herramientas para trabajar con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] artefactos.                                              |                 |       ✓        |
   |    **Artefactos**     |     Orquestación      |                               Una orquestación de ejemplo que puede usar para crear su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.                                |                 |       ✓        |
   | **Otros componentes** |     Instancias de prueba     |                           Prueba/muestra datos que puede usar como punto de partida para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución.                           |                 |                |
   | **Otros componentes** |           -            |                                                  Otros componentes de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)].                                                   |        ✓        |       ✓        |
   | **Otros componentes** | Explorador de configuración |                           Las aplicaciones usan para definir el registro para los almacenes de datos, configurar la validación específica de la entidad, asignación del encabezado, el procesamiento por lotes y los requisitos de confirmación.                            |        ✓        |       ✓        |
   | **Otros componentes** |          SDK           |                                    Contiene utilidades para esquemas de HL7 2.XML, como los componentes y los artefactos necesitan para el Tutorial de extremo a otro y la MLLP utilidades.                                     |        ✓        |       ✓        |
   | **Otros componentes** |   Plataforma de registro    |                                       Los componentes que admiten el registro de [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] eventos.                                        |        ✓        |       ✓        |
   | **Otros componentes** |    Proyecto de inicio     | Complemento para [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] que permite [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] desarrollo del proyecto. |        ✓        |       ✓        |


7. En **cuenta de servicio de registro**, escriba lo siguiente y, a continuación, seleccione **siguiente**.  


   |     Use     |                              Para                              |
   |------------------|----------------------------------------------------------------------|
   | **Nombre de cuenta** | Escriba el nombre de cuenta que desea usar para iniciar el servicio de registro. |
   |   **Contraseña**   |                 Escriba la contraseña para esta cuenta.                 |
   |    **Dominio**    |               Escriba el nombre de dominio para esta cuenta.                |


8. Cuando se le solicite **tiene concedido al nombre de cuenta de inicio de sesión como un servicio adecuado**, seleccione **Aceptar**.  

9. Revise el resumen y seleccione **siguiente**.  

10. Para el **carpeta de destino**, seleccione **siguiente** para usar la carpeta predeterminada. O bien, seleccione **cambio** para elegir una carpeta de instalación diferente.

11. En **información de base de datos de registro** página, escriba lo siguiente y, a continuación, seleccione **siguiente**.  


    |         Use         |                                                                                                                                                                                                                   Para                                                                                                                                                                                                                    |
    |--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Nombre del servidor de base de datos** |                                                                                                                              El valor predeterminado es el nombre del servidor. <br/><br/>**Tenga en cuenta** el nombre del servidor es el nombre del equipo que reside la base de datos BizTalkMgmtDb. No se puede cambiar este valor.                                                                                                                              |
    |  **Nombre de la base de datos de HL7**   | Escriba el nombre de la base de datos que contiene los datos para su [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] solución, o acepte el valor; predeterminado que es **BTAHL7**. <br/><br/> **Tenga en cuenta** debe usar el carácter ANSI-ASCII establecer según los requisitos de base de datos; [!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)] no admite otros juegos de caracteres. |


12. Seleccione **Instalar**.  

13. Seleccione **finalizar** finalizada.  

    > [!TIP] 
    > Seleccione **iniciar Tutorial** para instalar el Tutorial de extremo a otro.   

## <a name="next-steps"></a>Pasos siguientes
Paso a través de algunos tutoriales en [empezar a trabajar con el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md).
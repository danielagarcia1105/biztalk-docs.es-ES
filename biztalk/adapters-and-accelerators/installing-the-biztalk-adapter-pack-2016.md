---
title: Instalar BizTalk Adapter Pack 2016 | Microsoft Docs
description: Instalación típica o personalizada de BAP 2016, de 32 y 64 bits, instale en modo silencioso
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f3e1717-8063-4460-bfdc-a933cd58a5c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eef8511564f134f96745667b94f69f6fb263e17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000389"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a>Instalar BizTalk Adapter Pack 2016
Instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en las dos maneras siguientes:  

-   **En el modo interactivo**: ejecutar el Asistente para instalación  

-   **En modo silencioso**: usar la línea de comandos  

> [!IMPORTANT]
> - Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], independientemente de si está instalando utilizando el asistente o la línea de comandos.  
> - Ser que todos los [requisitos previos de software](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) instalados antes de instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].

## <a name="typical-vs-custom-installation"></a>Instalación personalizada de vs típico  
Enumera los tipos de instalación y las características que se instalan con cada opción:  

- El **típica** y **completar** opciones instalación todos los adaptadores con los proveedores de datos asociados. No tiene la posibilidad de elegir un adaptador específico para instalar.  

- El **personalizado** opción instala uno o más adaptadores, con los proveedores de datos asociados. Puede elegir qué adaptadores para instalar. Si elige instalar a un proveedor de datos, también debe instalar al adaptador correspondiente. Sin embargo, puede instalar a un adaptador sin necesidad de instalar al proveedor de datos correspondiente. Ello expandiendo el **ADO proveedores** nodo y, a continuación, seleccione los proveedores que no desea instalar. Consulte **instalar mediante el Asistente para instalación** (en este tema).  

   Por ejemplo, si instala el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], también debe instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]. Sin embargo, puede instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] sin necesidad de instalar el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  

## <a name="32-bit-and-64-bit-install-scenarios"></a>escenarios de instalación de 32 bits y 64 bits
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] se puede usar para: 

- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] tiempo de diseño (al generar los metadatos para las operaciones en las aplicaciones de línea de negocio)

- Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos)

  > [!NOTE]
  >  Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.  

- Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de línea de negocio)

Puede usar un único equipo para todas estas tardará entre, o use equipos diferentes. Dado que ambos [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar lo 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo donde completa las tareas de tiempo de diseño. 

### <a name="32-bit-install-scenario"></a>escenario de instalación de 32 bits
Instalar el software siguiente en cada equipo. Si usa un único equipo, todo el software debe instalarse en el equipo. 

1. Instalación de 32 bits [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]
2. Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].
3. Cliente de línea de negocio de 32 bits de instalación y otras requieren los archivos DLL.  

### <a name="64-bit-install-scenarios"></a>escenarios de instalación de 64 bits

|                                                                                                                 Para el tiempo de diseño de Visual Studio                                                                                                                  |                                                                                                                  MMC de BizTalk para tiempo de diseño                                                                                                                   |                                                                                                                                                                                                                                                                                                         Para el tiempo de ejecución de BizTalk                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                Para el diseño de Visual Studio de tiempo o tiempo de diseño de BizTalk MMC + BizTalk tiempo de ejecución                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 32 bits y otro archivos DLL necesarios. | -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 32 bits y otro archivos DLL necesarios. | **Para un proceso de BizTalk de 32 bits**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 32 bits y otro archivos DLL necesarios.<br /><br /> **Para un proceso de 64 bits BizTalk**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 64 bits y otro archivos DLL necesarios. | **Para un proceso de BizTalk de 32 bits**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 32 bits y otro archivos DLL necesarios.<br /><br /> **Para un proceso de 64 bits BizTalk**:<br /><br /> -Install 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Install 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 64 bits y otro archivos DLL necesarios.<br /><br /> -Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de línea de negocio de 32 bits y otro archivos DLL necesarios. |

> [!NOTE]
>  En cualquier equipo donde desea realizar tareas de tiempo de diseño, utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  

## <a name="install-using-the-setup-wizard"></a>Instalación mediante el Asistente para instalación  
Pasos para instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo.  

1. Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.  

2. Seleccione **instalar adaptadores de Microsoft BizTalk**. En la ventana siguiente, se enumeran los programas de requisitos previos que falten. Si falta alguno, a continuación, seleccione el programa que falta, y el programa de instalación lo instala automáticamente. 

   Por ejemplo, seleccione **paso 2: instalar Microsoft BizTalk Adapter Pack** o **paso 3: instalar Microsoft BizTalk Adapter Pack (x64)**.  

   > [!NOTE]
   >  Si está instalando el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en una máquina virtual, el Asistente para instalación puede mostrar un mensaje que se comprueba si hay espacio en disco disponible. Si aparece este mensaje deje de responder o simplemente se queda allí, se recomienda **instalar en modo silencioso** (en este tema).  

3. En la pantalla de bienvenida, seleccione **siguiente**.  

4. Acepte el contrato de licencia del usuario final (CLUF) y, a continuación, seleccione **siguiente**.  

5. En **Elegir tipo de instalación**:  

   -   Para instalar las características más comunes, seleccione **típica**.  

   -   Para seleccionar los adaptadores que desea instalar, seleccione **personalizado**y, a continuación, continúe con el paso siguiente.  

   -   Para instalar todas las características, seleccione **completar**.  

       > [!IMPORTANT]
       >  Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server.  

6. **Para quitar Microsoft **en el equipo, seleccione**quitar y, a continuación, vaya al paso 10. Cambiar la instalación de BAP en modo silencioso  

    1.  Consulte la tabla en **instalar BizTalk Adapter Pack en modo silencioso** (en este tema) para obtener información acerca de los valores que puede usar para estas propiedades.  

    2.  Para los adaptadores que no desea, seleccione el icono junto al adaptador y, a continuación, seleccione **característica completa no estará disponible**.  

    3.  Expanda **ADO proveedores**y, a continuación, seleccione los proveedores que no desea instalar.  

    4.  Seleccione **Siguiente**.  

7. Seleccione **Instalar**.  

8. En **Customer Experience Improvement Program**, puede elegir para inscribirse. Si inscribe, con Microsoft puede compartir los datos siguientes:  

   - Datos relacionados con el hardware del equipo en el que está instalando el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  

   - Datos relacionados con las versiones de aplicación empresarial se usa con el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  

     [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) proporciona más información.  

     Seleccione **Aceptar**. 

   > [!NOTE]
   >  Siempre puede cambiar esta configuración mediante la ejecución del programa de instalación en modo de reparación de **programas**.  

9. Seleccione **Finalizar**.  

<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a>Instalar en modo silencioso  
 Use la **msiexec** comando para realizar una instalación silenciosa. Como parte del comando msiexec, especifique los componentes individuales que desea instalar. En la tabla siguiente se enumera los valores para cada componente en el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Use estos valores para instalar componentes específicos (o quitar). Para instalar (o quitar) más de un componente, puede usar una combinación de estos valores separados por punto y coma.  


|                                    Nombre de componente                                    |                                                                Valor correspondiente para las propiedades de línea de comandos                                                                 |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        |                                                                                   DbFeature                                                                                    |
| [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] |                                                                                OracleEBSFeature                                                                                |
|           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |                                                                             SapBaseAdapterFeature                                                                              |
|        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |                                                                            SiebelBaseAdapterFeature                                                                            |
|            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |                                                                                   SqlFeature                                                                                   |
|        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |     SapAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si está instalando el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] también.      |
|     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | SiebelAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si está instalando el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] también. |
|                                    Todos los componentes                                    |                                                                                      ALL                                                                                       |

> [!IMPORTANT]
>  Los nombres de función distinguen mayúsculas de minúsculas.  

 Los pasos siguientes muestran cómo completar una instalación silenciosa de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para los distintos componentes.  

### <a name="silent-mode-steps"></a>Pasos de modo silencioso

1. Abra un símbolo del sistema y vaya a la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] raíz en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.  

2. Ejecute los comandos siguientes en función de lo que desea instalar:  

   > [!NOTE]
   >  Para realizar una instalación silenciosa en una plataforma basado en x64 64, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi` en los siguientes comandos.  

   - Para llevar a cabo una instalación completa, que se instala todos los adaptadores incluidos los proveedores de datos de .NET Framework, escriba:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
     ```  

   - Para instalar solo el [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
     ```  

   - Para instalar solo el [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
     ```  

   - Para instalar solo el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
     ```  

   - Para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] junto con [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
     ```  

   - Para instalar solo el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
     ```  

   - Para instalar el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] junto con [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
     ```  

   - Para instalar solo el [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
     ```  

   - Para instalar a todos los adaptadores de bases, escriba:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
     ```  

   - Para instalar a los dos proveedores de datos de .NET Framework, escriba:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
     ```  

   - Cualquier tipo de instalación personalizada mediante la separación de los componentes por una coma. Por ejemplo, para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] con el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]y el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
     ```  

   - También puede decidir para inscribirse en CEIP como parte de la instalación silenciosa. Tipo:  

     ```  
     msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
     ```  

      De forma predeterminada, la opción es false. 

     > [!IMPORTANT]
     >  Al instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] versión de evaluación en modo silencioso, la opción predeterminada para el CEIP es true.  

     Para obtener más información sobre la **msiexec** comando, escriba `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [ http://go.microsoft.com/fwlink/p/?LinkId=103199 ](http://go.microsoft.com/fwlink/p/?LinkId=103199).

## <a name="known-install-issue"></a>Problema de instalación conocidos
Para obtener una lista completa de los problemas relacionados con la instalación, consulte **Troubleshooting** para cada adaptador.  

**Ejecutar programa de instalación en un equipo de 64 bits puede producir un error al obtener acceso al archivo de esquema**  

El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] el programa de instalación produce un error al obtener acceso a la Microsoft.Adapters. *\<AdapterName\>*_schema.xml archivo, pero continúa con la instalación del adaptador.  

**Causa**  

Si las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] están instalados en el mismo equipo, el archivo de esquema de destino utilizado por ambas es el mismo. Como resultado, se instala el archivo de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] podría estar en uso por IIS, cuando el instalador de 64 bits intenta tener acceso a él.  

**Resolución**  

Copiar manualmente el Microsoft.Adapters.  *\<AdapterName\>* archivo _schema.xml desde *C:\Program Files\Microsoft BizTalk adaptador Pack (x64) \IIS esquemas* a *C:\Windows\System32\inetsrv\ config\schema*. 

## <a name="next-step"></a>Paso siguiente
[Pasos posteriores a la instalación](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)
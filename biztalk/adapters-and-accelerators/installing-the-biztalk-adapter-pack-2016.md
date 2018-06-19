---
title: Instalar BizTalk Adapter Pack 2016 | Documentos de Microsoft
description: La instalación típica o personalizada de BAP 2016, de 32 y 64 bits, instalar en modo silencioso
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
ms.openlocfilehash: 7076b9c076b263a54a436c553b519671760ca473
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967794"
---
# <a name="install-the-biztalk-adapter-pack-2016"></a>Instalar BizTalk Adapter Pack 2016
Instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] de las dos maneras siguientes:  
  
-   **En el modo interactivo**: ejecutar el Asistente para la instalación  
  
-   **En modo silencioso**: usar la línea de comandos  
  
> [!IMPORTANT]
> - Debe tener privilegios administrativos en el equipo donde se instala el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], independientemente de si está instalando utilizando el asistente o la línea de comandos.  
> - Estar seguro de que todos los [requisitos previos de software](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) instalado antes de instalar la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].

## <a name="typical-vs-custom-installation"></a>Instalación personalizada de vs típico  
Enumera los tipos de instalación y las características que se instalan con cada opción:  
  
-   El **típica** y **completar** opciones instalación todos los adaptadores, con los proveedores de datos asociados. No tiene la posibilidad de elegir un adaptador específico para instalar.  
  
-   El **personalizado** opción instala uno o varios adaptadores, con los proveedores de datos asociados. Puede elegir qué adaptadores para instalar. Si decide instalar a un proveedor de datos, también debe instalar al adaptador correspondiente. Sin embargo, puede instalar a un adaptador sin necesidad de instalar al proveedor de datos correspondiente. Esto se hace al expandir el **ADO proveedores** nodo y, a continuación, seleccione los proveedores que no desea instalar. Vea **instalar mediante el Asistente para instalación** (en este tema).  
  
     Por ejemplo, si instala el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], también debe instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]. Sin embargo, puede instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] sin necesidad de instalar la [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].  
  
## <a name="32-bit-and-64-bit-install-scenarios"></a>escenarios de instalación de 32 bits y 64 bits
 Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] puede utilizarse para: 
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]tiempo de diseño (cuándo generar metadatos para las operaciones en las aplicaciones LOB)
  
-   Tiempo de diseño de consola de administración de BizTalk Server (para la creación de puertos físicos)
  
    > [!NOTE]
    >  Consola de administración de BizTalk Server se ejecuta como una aplicación de Microsoft Management Console (MMC) de 32 bits.  
  
-   Tiempo de ejecución de BizTalk (al enviar y recibir mensajes desde aplicaciones de LOB)

Puede usar un único equipo para todos estos tardará entre o utiliza equipos diferentes. Dado que ambos [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y MMC de BizTalk son procesos de 32 bits, debe instalar el 32-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en el equipo donde se realizarán las tareas de tiempo de diseño. 

### <a name="32-bit-install-scenario"></a>escenario de instalación de 32 bits
Instalar el software siguiente en cada equipo. Si está utilizando un único equipo, todo el software debe instalarse en el equipo. 
 
1. Instalación de 32 bits[!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)]
2. Instalación de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].
3. Cliente LOB de 32 bits de instalación y otro requieren archivos DLL.  
  
### <a name="64-bit-install-scenarios"></a>escenarios de instalación de 64 bits
  
|Para tiempo de diseño de Visual Studio|MMC de BizTalk para tiempo de diseño|Tiempo de ejecución de BizTalk|Para el diseño de Visual Studio de hora o tiempo de diseño de BizTalk MMC + BizTalk tiempo de ejecución|  
|---|---|---|---|  
|-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|-Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|**Para un proceso de BizTalk de 32 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.<br /><br /> **Para un proceso de BizTalk de 64 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.|**Para un proceso de BizTalk de 32 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.<br /><br /> **Para un proceso de BizTalk de 64 bits**:<br /><br /> -Instalar 64-bit [!INCLUDE[afproductnameshort](../includes/afproductnameshort-md.md)].<br /><br /> -Instalar 64-bit [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 64 bits de LOB y otro archivos DLL necesarios.<br /><br /> -Instalar 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].<br /><br /> -Instalar el cliente de 32 bits de LOB y otro archivos DLL necesarios.|  
  
> [!NOTE]
>  En cualquier equipo donde desea realizar tareas de tiempo de diseño, utilizando [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] o MMC de BizTalk, debe instalar lo 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
## <a name="install-using-the-setup-wizard"></a>Instalar mediante el Asistente para la instalación  
Pasos para instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en modo interactivo.  
  
1.  Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **setup.exe**.  
  
2.  Seleccione **instalar adaptadores de Microsoft BizTalk**. En la ventana siguiente, se enumeran los programas de requisitos previos que falten. Si falta alguno, a continuación, seleccione el programa que falta y el programa de instalación lo instala automáticamente. 

    Por ejemplo, seleccione **paso 2: instalar Microsoft BizTalk Adapter Pack** o **paso 3: instalar Microsoft BizTalk Adapter Pack (x64)**.  
  
    > [!NOTE]
    >  Si va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] en una máquina virtual, el Asistente para instalación puede mostrar un mensaje que se comprueba si hay espacio disponible en disco. Si aparece este mensaje de bloqueo o simplemente sentarse, le recomendamos que **instalar en modo silencioso** (en este tema).  
  
3.  En la pantalla de bienvenida, seleccione **siguiente**.  
  
4.  Acepte el contrato de licencia para el usuario final (CLUF) y, a continuación, seleccione **siguiente**.  
  
5.  En **Elegir tipo de instalación**:  
  
    -   Para instalar las características más comunes, seleccione **típica**.  
  
    -   Para seleccionar los adaptadores que desea instalar, seleccione **personalizada**y, a continuación, continúe con el paso siguiente.  
  
    -   Para instalar todas las características, seleccione **completar**.  
  
        > [!IMPORTANT]
        >  Para instalar sólo el adaptador que usa para comunicarse con la aplicación de empresa, seleccione la **personalizado** instalación.  
  
6. **Necesario** sólo si eligió la instalación personalizada. Si ha elegido el **típica** o **completar** instalación, a continuación, omita este paso y vaya al paso 7.  
  
    1.  En **personalizada**, expanda **Base adaptadores** para ver el número de adaptadores disponible.  
  
    2.  Para los adaptadores que no desea, seleccione el icono al lado del adaptador y, a continuación, seleccione **característica completa no estará disponible**.  
  
    3.  Expanda **ADO proveedores**y, a continuación, seleccione los proveedores que no desea instalar.  
  
    4.  Seleccione **Siguiente**.  
  
7.  Seleccione **Instalar**.  
  
8.  En **Customer Experience Improvement Program**, puede elegir para inscribirse. Si inscribe, puede compartir los siguientes datos con Microsoft:  
  
    -   Datos relacionados con el hardware del equipo en el que va a instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
    -   Datos relacionados con las versiones de aplicación de empresa que usa con la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
  
     [CEIP](http://go.microsoft.com/fwlink/p/?LinkId=144699) proporciona más información.  
     
     Seleccione **Aceptar**. 
  
    > [!NOTE]
    >  Siempre puede cambiar esta configuración mediante la ejecución de la instalación en modo de reparación de **programas**.  
  
9. Seleccione **Finalizar**.  
  
<a name="BKMK_SilentInst"></a>   
## <a name="install-in-silent-mode"></a>Instalar en modo silencioso  
 Use la **msiexec** comando para realizar una instalación silenciosa. Como parte del comando msiexec, escriba los componentes individuales que desea instalar. En la tabla siguiente se enumera los valores para cada componente en el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]. Utilice estos valores para instalar componentes específicos (o quitar). Para instalar (o quitar) más de un componente, puede usar una combinación de estos valores separados por punto y coma.  
  
|Nombre de componente|Valor correspondiente para las propiedades de línea de comandos|  
|---|---|  
|[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|DbFeature|  
|[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|OracleEBSFeature|  
|[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|SapBaseAdapterFeature|  
|[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|SiebelBaseAdapterFeature|  
|[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|SqlFeature|  
|[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|SapAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] también.|  
|[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|SiebelAdoFeature<br /><br /> **Tenga en cuenta**: debe proporcionar este valor solo si va a instalar la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] también.|  
|Todos los componentes|ALL|  
  
> [!IMPORTANT]
>  Los nombres de función distinguen mayúsculas de minúsculas.  
  
 Los pasos siguientes muestran cómo realizar una instalación silenciosa de [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] para los distintos componentes.  
  
### <a name="silent-mode-steps"></a>Pasos de modo silencioso
  
1.  Abra un símbolo del sistema y vaya a la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] raíz en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación.  
  
2.  Ejecute los comandos siguientes en función de lo que va a instalar:  
  
    > [!NOTE]
    >  Para realizar una instalación silenciosa en una plataforma basada en x64, reemplace `AdaptersSetup.msi` con `AdaptersSetup64.msi` en los siguientes comandos.  
  
    -   Para llevar a cabo una instalación completa, que se instala todos los adaptadores incluidos los proveedores de datos de .NET Framework, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=ALL  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=DbFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=OracleEBSFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature  
        ```  
  
    -   Para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] junto con [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature  
        ```  
  
    -   Para instalar el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] junto con [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SiebelBaseAdapterFeature,SiebelAdoFeature  
        ```  
  
    -   Para instalar solo la [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SqlFeature  
        ```  
  
    -   Para instalar a todos los adaptadores de base, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SiebelBaseAdapterFeature,DbFeature,OracleEBSFeature,SqlFeature  
        ```  
  
    -   Para instalar a los dos proveedores de datos de .NET Framework, escriba:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapAdoFeature,SiebelAdoFeature  
        ```  
  
    -   Cualquier tipo de instalación personalizada mediante la separación de los componentes por una coma. Por ejemplo, para instalar el [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] con el [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]y el [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)] tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn ADDLOCAL=SapBaseAdapterFeature,SapAdoFeature,SiebelBaseAdapterFeature  
        ```  
  
    -   También puede optar por inscribirse en CEIP como parte de la instalación silenciosa. Tipo:  
  
        ```  
        msiexec /i AdaptersSetup.msi /qn CEIP_OPTIN=true  
        ```  
  
         De forma predeterminada, la opción es false. 
  
        > [!IMPORTANT]
        >  Al instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] versión de evaluación en modo silencioso, la opción predeterminada para el CEIP es true.  
  
     Para obtener más información sobre la **msiexec** de comandos, escriba `msiexec` en la línea de comandos y presione `ENTER`. O vaya a [http://go.microsoft.com/fwlink/p/?LinkId=103199](http://go.microsoft.com/fwlink/p/?LinkId=103199).
     
## <a name="known-install-issue"></a>Problema de instalación conocidos
Para obtener una lista completa de los problemas relacionados con la instalación, consulte **solución de problemas** para cada adaptador.  
  
**Ejecuta la instalación en un equipo de 64 bits puede producir un error al obtener acceso al archivo de esquema**  
  
El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] el programa de instalación produce un error al obtener acceso a la Microsoft.Adapters. *\<AdapterName\>*_schema.xml archivo, pero continúa con la instalación del adaptador.  
  
**Causa**  
  
Si las versiones de 32 bits y 64 bits de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] están instalados en el mismo equipo, el archivo de esquema de destino utilizado es el mismo. Como resultado, se instala el archivo de 32 bits [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] podría estar utilizando IIS cuando el programa de instalación de 64 bits intenta tener acceso a él.  
  
**Resolución**  
  
Copie manualmente el Microsoft.Adapters.  *\<AdapterName\>* archivo _schema.xml desde *C:\Program Files\Microsoft BizTalk adaptador Pack (x64) \IIS esquemas* a *C:\Windows\System32\inetsrv\ config\schema*. 
  
## <a name="next-step"></a>Paso siguiente
[Pasos posteriores a la instalación](../adapters-and-accelerators/post-installation-steps-for-biztalk-adapter-pack-2016.md)
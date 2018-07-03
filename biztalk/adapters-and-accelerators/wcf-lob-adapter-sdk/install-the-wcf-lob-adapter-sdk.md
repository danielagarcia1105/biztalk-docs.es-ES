---
title: Instalar el SDK del adaptador LOB de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95fba9830bd97dd619cd16d18c0363a4525d1397
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999709"
---
# <a name="install-the-wcf-lob-adapter-sdk"></a>Instalar el SDK del adaptador LOB de WCF
Instalar y configurar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]. 

## <a name="requirements"></a>Requisitos 
Instalar los siguientes componentes en el sistema donde se instala el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. 

> [!NOTE]
> **Para obtener una lista de las versiones admitidas**, consulte: 
> 
> [Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016)  
> [Requisitos de hardware y software de BizTalk Server 2013 y 2013 R2](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)

|                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                         Windows                                          | x86 o x64 <br/><br/>Incluyen recursos del sistema operativo necesarios:<br/> <ul><li>Microsoft Distributed Transaction Coordinator (MSDTC): Debe para admitir las transacciones de OleTx</li><li>Message Queue Server (MSMQ): Debe para admitir la mensajería de confianza</li><li>Internet Information Services (IIS): Necesario si desea hospedar su aplicación en IIS</li><li>Windows Process Activation Service (WAS): Necesario si desea hospedar su aplicación en WAS</li></ul> |
|                             Windows Communication Foundation                             |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|        [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]        |                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|       [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)]       |                                                                                                                                     Necesario si va a crear adaptadores personalizados, o desarrollar soluciones que utilizan los adaptadores creado con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].                                                                                                                                      |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] |                                                                                                                                                                 Es necesario si se usan los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                                 |

## <a name="install"></a>Install

> [!IMPORTANT]
> * Cierre todas las instancias de Visual Studio
> * Para realizar un **completar** programa de instalación, confirme que BizTalk Server está instalado en el equipo.  

1. Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** como administrador.

2. Seleccione **instalar Microsoft BizTalk Adapters**y, a continuación, seleccione **instalar el SDK de Microsoft WCF LOB adaptador**.  

3. En el **bienvenida** pantalla, seleccione **siguiente**.  

4. Acepte el contrato de licencia y seleccione **Siguiente**.  

5. En **Elegir tipo de instalación**, seleccione el tipo de instalación:  

   -   Para instalar las herramientas y el tiempo de ejecución comunes, seleccione **típica**.  

   -   Para seleccionar las características que desea instalar y la ubicación de instalación, seleccione **personalizado**y, a continuación, seleccione las características que desea instalar.  

   -   Para instalar todas las características, seleccione **completar**.  

6. Seleccione **Instalar**.  

## <a name="update-or-remove"></a>Actualice o quite

1. Abra **programas y características**. 

2. En la lista, seleccione **SDK de adaptador LOB de Windows Communication Foundation**y, a continuación, seleccione **cambio**.  

3. En el **bienvenida** pantalla, seleccione **siguiente**.  

4. Realice una de las siguientes operaciones:  

   - Para seleccionar los componentes que desea instalar, seleccione **cambio**.  

   - Para reparar los errores en la instalación más reciente, seleccione **reparar**.  

   - Para quitar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en el equipo, seleccione **quitar**.  

5. Si decide modificar la instalación:  

   1.  Seleccione **Siguiente**.  

   2.  Seleccione **cambio**y, a continuación, seleccione **finalizar**.  

6. Si elige reparar la instalación, en el **preparado para reparar el SDK de adaptador LOB de WCF** cuadro de diálogo, seleccione **reparar**y, a continuación, seleccione **finalizar**.  

7. Si decide quitar los adaptadores, en el **listo para quitar el SDK de adaptador LOB de WCF** cuadro de diálogo, seleccione **quitar**y, a continuación, seleccione **finalizar**.  


#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a>Quitar los adaptadores personalizados después de desinstalar el SDK de adaptador LOB de WCF  

 Si ha desarrollado los adaptadores personalizados mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]y estos adaptadores se han registrado en el equipo, también debe completar el procedimiento siguiente.  

1.  Quitar el adaptador personalizado de la caché global de ensamblados (GAC).  

    1.  Abra un **símbolo del sistema de Visual Studio**.  

    2.  Quitar personalizado **adaptador .dll** desde la GAC mediante **comandos gacutil /u**.  

2.  Quite las referencias para el enlace del adaptador personalizado de machine.config.  

    1.  Vaya al archivo machine.config en \< *unidadDelSistema*\>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.  

    2.  Abra el archivo con un editor de texto.  

    3.  Busque el elemento bindingExtensions, cliente y bindingElementExtensions en system.serviceModel\extensions.  

    4.  Quite el enlace WCF que pertenece a un adaptador personalizado.  

## <a name="do-a-silent-installation"></a>Realizar una instalación silenciosa  
 Una instalación silenciosa es ideal para escenarios de prueba o como parte de una implementación empresarial a gran escala. [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Proporciona los parámetros de línea de comandos que puede usar con AdapterFramework.msi para realizar una instalación silenciosa.  

> [!NOTE]
>  Para realizar una instalación silenciosa, debe ser un administrador en el equipo. 


1. Abra un símbolo del sistema como administrador.  

2. Escriba lo siguiente:

   ```  
   AdapterFramework.msi /quiet MUOPTIN=”Yes”  
   ```  

   Utilice las siguientes opciones de línea de comandos junto con AdapterFramework.msi:  

   * Use `/quiet` instalar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en modo silencioso.  

   * Usar MUOPTIN = "Yes"&#124;"No" para indicar si el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] debe buscar actualizaciones con Microsoft Update.  

       Cuando se establece en Sí, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] busca actualizaciones a través de Microsoft Update. Cuando se establece en no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no buscar actualizaciones con Microsoft Update.  

> [!NOTE]
>  Para mostrar las opciones adicionales para la instalación de línea de comandos, escriba `AdapterFramework.msi /?`en el símbolo del sistema.  


---
title: Requisitos previos para crear aplicaciones Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c08f853-7f72-4e08-aa63-debdab68c972
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeea15b7a05eb50b498c4c177c987f5c5c736a85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-to-create-siebel-applications"></a>Requisitos previos para crear aplicaciones de Siebel
¿Qué debe hacer antes de desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. El tema también enumeran algunas herramientas de BizTalk Server que se utilizan para desarrollar aplicaciones de BizTalk.  
  
## <a name="create-a-strong-named-key-file"></a>Crear un archivo de claves con nombre seguro

Debe crear un archivo de clave de nombre seguro para generar proyectos en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Un nombre seguro consta de la identidad del proyecto, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona); Además de una clave pública y una firma digital. El archivo de clave de nombre seguro contiene la clave pública y la clave privada.  
  
> [!IMPORTANT]
>  Crear un archivo de clave de nombre seguro es una tarea única. Puede usar la misma clave para todas las aplicaciones de BizTalk que desarrolla.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Debe tener Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] instalado en el equipo donde desea crear una clave de nombre seguro.  
  
### <a name="create-a-strong-name-key-file"></a>Crear un archivo de clave de nombre seguro  
  
1.  Abra el símbolo del sistema para desarrolladores de Visual Studio.  
  
2.  En el símbolo del sistema, navegue a la ubicación donde desea crear el archivo de clave. Por ejemplo, escriba `cd C:\Sample`, y, a continuación, presione ENTRAR.  
  
3.  En el símbolo del sistema, escriba `sn -k <key file name>.snk`, y, a continuación, presione ENTRAR.  
  
    > [!NOTE]
    >  Debería recibir un mensaje en el símbolo del sistema que indica que el par de claves se escribió en el archivo de clave de nombre seguro.  
  
4.  En el símbolo del sistema, escriba `exit`, y, a continuación, presione ENTRAR.  
  
## <a name="learn-the-biztalk-server-tools"></a>Obtenga información acerca de las herramientas de BizTalk Server

Los temas sobre cómo usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en [bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md) se escriben con la suposición de que tiene conocimientos prácticos de un número de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas. Use las siguientes herramientas para desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersiebel_md](../../includes/adaptersiebel-md.md)]:  
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 
  
-   Explorador de BizTalk  
  
-   Eesigner de orquestación  
  
-   Diseñador de canalizaciones  
  
-   Asignador de BizTalk  
  
-   Consola de administración de BizTalk Server  
  
### <a name="prerequisites"></a>Requisitos previos  
 Debe instalar Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] antes de que puede tener acceso a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] herramientas.  
  
### <a name="biztalk-server-tools"></a>Herramientas de BizTalk Server  
 En la tabla siguiente incluye los temas de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación que explica cómo usar cada una de las herramientas enumeradas.  
  
|Herramienta|Temas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación principal|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]|-   [Con Visual Studio](../../core/using-visual-studio.md) <br />-   [Trabajar con proyectos de BizTalk](../../core/working-with-biztalk-projects.md)<br />-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).|  
|Diseñador de orquestaciones|[Crear orquestaciones mediante el Diseñador de orquestaciones](../../core/creating-orchestrations-using-orchestration-designer.md)|  
|Diseñador de canalizaciones| [Crear canalizaciones mediante el Diseñador de canalizaciones](../../core/creating-pipelines-using-pipeline-designer.md)|  
|Asignador de BizTalk| [Crear asignaciones usando al asignador de BizTalk](../../core/creating-maps-using-biztalk-mapper.md)|  
|Consola de administración de BizTalk Server|[Uso de la consola de administración de BizTalk Server](../../core/using-the-biztalk-server-administration-console.md)|  
  
## <a name="next"></a>Siguiente
[Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)
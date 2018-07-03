---
title: Requisitos previos para crear aplicaciones de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51ae9569-4081-4142-9ee2-8ae0069e9d90
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72225a059d5b655555f46f06758df11de3eaa8e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978573"
---
# <a name="prerequisites-to-create-sap-applications"></a>Requisitos previos para crear aplicaciones de SAP
Esta sección proporciona información acerca de las tareas que se deben realizar antes de desarrollar aplicaciones de BizTalk con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. También se mencionan algunas herramientas de BizTalk Server que se usan para desarrollar aplicaciones de BizTalk.  

## <a name="create-a-strong-name-key-file"></a>Crear un archivo de clave de nombre seguro

Debe crear un archivo de clave de nombre seguro para generar proyectos en Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Un nombre seguro consta de la identidad del proyecto, su nombre de texto simple, el número de versión y la información de referencia cultural (si se proporciona), más una clave pública y una firma digital. El archivo de clave de nombre seguro contiene la clave pública y la clave privada.  

> [!IMPORTANT]
>  Creación de un archivo de clave de nombre seguro es una tarea única. Puede usar la misma clave para todas las aplicaciones de BizTalk que desarrolla.  

1.  Abra el símbolo del sistema para desarrolladores de Visual Studio.  

2.  Vaya a la ubicación donde desea crear el archivo de clave en el símbolo del sistema. Por ejemplo, escriba **cd C:\Sample**, y, a continuación, presione ENTRAR.  

3.  En el símbolo del sistema, escriba `sn -k <key file name\>.snk`, y, a continuación, presione ENTRAR.  

    > [!NOTE]
    >  Debería recibir un mensaje en el símbolo del sistema que indica que se ha escrito el par de claves para el archivo de clave de nombre seguro.  

4.  En el símbolo del sistema, escriba **salir**, y, a continuación, presione ENTRAR.  

## <a name="learn-the-biztalk-server-tools"></a>Obtenga información sobre las herramientas de BizTalk Server

Los temas sobre cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en [BizTalk desarrollar aplicaciones](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md) suponga que tiene conocimientos prácticos de un número de herramientas de BizTalk Server. Usará las siguientes herramientas para desarrollar aplicaciones de BizTalk con [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]:  

- Microsoft [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] 

- Orquestación eesigner  

- Diseñador de canalizaciones  

- Asignador de BizTalk  

- Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]  


### <a name="prerequisites"></a>Requisitos previos  
 Debe instalar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para poder tener acceso a las herramientas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

### <a name="biztalk-server-tools"></a>Herramientas de BizTalk Server  
 En la tabla siguiente incluye los temas de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación que explica cómo usar cada una de las herramientas enumeradas.  


|                                   Herramienta                                    |                                                                                                                                                                                              Temas de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] documentación principal                                                                                                                                                                                               |
|---------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] | -   [Con Visual Studio](../../core/using-visual-studio.md) <br />-   [Trabajar con proyectos de BizTalk](../../core/working-with-biztalk-projects.md)<br />-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx). |
|                          Diseñador de orquestaciones                           |                                                                                                                                                                                          [Crear orquestaciones mediante el Diseñador de orquestaciones](../../core/creating-orchestrations-using-orchestration-designer.md)                                                                                                                                                                                           |
|                             Diseñador de canalizaciones                             |                                                                                                                                                                                                    [Crear canalizaciones mediante el Diseñador de canalizaciones](../../core/creating-pipelines-using-pipeline-designer.md)                                                                                                                                                                                                     |
|                              Asignador de BizTalk                               |                                                                                                                                                                                                            [Creación de mapas mediante el asignador de BizTalk](../../core/creating-maps-using-biztalk-mapper.md)                                                                                                                                                                                                             |
|                   Consola de administración de BizTalk Server                   |                                                                                                                                                                                               [Utilizar la consola de administración de BizTalk Server](../../core/using-the-biztalk-server-administration-console.md)                                                                                                                                                                                                |

## <a name="next"></a>Siguiente
[Bloques de creación para crear aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)
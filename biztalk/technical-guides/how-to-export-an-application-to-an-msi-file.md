---
title: "Cómo exportar una aplicación a un archivo .msi | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7179e86-aa55-426b-a0db-19229ca5625a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600118718585401d9ba6c3158b6510af55c53e74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-an-application-to-an-msi-file"></a>Cómo exportar una aplicación a un archivo .msi
Puede usar el Asistente para exportar archivos MSI o BTSTask para exportar los artefactos de la aplicación a un archivo MSI que se va a usar para importar la aplicación a un nuevo grupo de BizTalk. Este proceso también instalará la aplicación en los equipos que vayan a ejecutarla.  
  
## <a name="exporting-application-bindings-in-an-msi-file"></a>Exportar enlaces de la aplicación en un archivo .msi  
 Al exportar una aplicación a un archivo .msi, puede seleccionar qué recursos para exportar. Estos recursos pueden incluir todos o un subconjunto de los ensamblados implementados o enlaces que están disponibles para exportación.  
  
 Para que sea más fácil importar las aplicaciones en el entorno de desarrollo en un momento posterior para realizar cambios o adiciones, puede que desee exportar los enlaces para cada aplicación y, a continuación, agregarlas de nuevo a las aplicaciones. Cuando se establece el tipo de recurso para el "Tipo", puede agregar archivos de enlace adicionales a un archivo MSI. Para cada archivo de enlace que agregue, debe especificar el nombre de entorno (campo de texto) que se deben aplicar los enlaces. A continuación, en la importación, deberá seleccionar el nombre del entorno al que está importando actualmente. Si éstos coinciden, el archivo de enlace se aplica al grupo de destino. También no puede especificar ningún nombre de entorno para el archivo de enlace agregados, lo que hará que el conjunto de enlaces que se aplicará a todos los entornos de forma incondicional.  
  
 El uso de un archivo .msi automatiza lo que en caso contrario, se puede sustancialmente establecer de las tareas manuales. En un entorno de producción, puede realizar más fácil de implementar un ensamblado en varios grupos de BizTalk mediante el transporte de los enlaces del ensamblado junto con el ensamblado. Si la aplicación contiene un número significativo de artefactos, puede exportar algunos de los artefactos a un paquete de Windows Installer y algunas en uno o varios paquetes de Windows Installer.  
  
 Al exportar la aplicación, debe tener en cuenta algunos puntos importantes. Por ejemplo, puede exportar todos los artefactos de la aplicación o solo los artefactos que desea agregar o actualizar. Si exporta un artefacto de archivo, asegúrese de que se trate de la versión que desea usar en la aplicación. Para más dichos puntos y para obtener más información acerca de cómo exportar una aplicación de BizTalk a un archivo .msi, consulte [cómo exportar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154848) (http://go.microsoft.com/fwlink/?LinkID=154848).
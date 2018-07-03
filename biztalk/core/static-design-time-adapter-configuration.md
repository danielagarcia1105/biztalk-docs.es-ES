---
title: Configuración estática en tiempo de diseño de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 332723a4-e39d-43f5-af4d-bf9f56496535
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c865acca81228a18e027b5b65a7488965eeb7d46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972509"
---
# <a name="static-design-time-adapter-configuration"></a>Configuración estática de adaptador en tiempo de diseño
La parte de tiempo de diseño del adaptador se encarga de definir todas las propiedades disponibles y de validar la entrada del usuario. En una configuración estática en tiempo de diseño, el adaptador usa la interfaz de usuario predeterminada (UI) para mostrar y editar sus propiedades.  
  
 En esta sección se explica cómo se implementa la función de configuración estática en tiempo de diseño para el adaptador personalizado. Los cambios que decida hacer se basarán en las necesidades de las aplicaciones con las que el adaptador se comunica y la lógica que el adaptador necesita implementar. Vínculos a secciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se proporciona ayuda que describe estos pasos con más detalle o proporciona información adicional cuando esté disponible. Además, resalta los lugares de la documentación del adaptador de archivo de ejemplo donde hay ejemplos relevantes.  
  
## <a name="guidelines-for-the-static-development-process"></a>Directrices del proceso de desarrollo estático  
 La lista siguiente contiene recomendaciones para generar la funcionalidad estática en tiempo de diseño en el adaptador. Durante el desarrollo, es posible que no sea necesario efectuar todos estos pasos ni seguirlos en orden estricto.  
  
1. Cree una lista de los requisitos de configuración del adaptador y de los parámetros de configuración que necesite definir. Si los parámetros se usan de forma global para todas las ubicaciones de recepción y puertos de envío, especifíquelos en el archivo de configuración de esquema del controlador. Si son específicos del puerto o la ubicación, configúrelos en los archivos de configuración del puerto de envío y de la ubicación de recepción.  
  
2. Modifique las páginas de propiedades del adaptador par registrar los parámetros de configuración nuevos. Para obtener información sobre este paso, consulte [esquemas de configuración de adaptador](../core/adapter-configuration-schemas.md).  
  
3. Modifique la vista de árbol de las categorías de esquema mediante el Asistente para agregar metadatos de adaptador. Para obtener más información sobre este paso, consulte [categorías de esquema en el Asistente para agregar metadatos de adaptador](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)  
  
4. Modifique el código de ejemplo para que devuelva esquemas como archivos Lenguaje de descripción de servicios web (WSDL). Para obtener más información sobre este paso, consulte [IStaticAdapterConfig de adaptador estático de interfaz](../core/static-adapter-istaticadapterconfig-interface.md).  
  
5. Modifique los archivos de WSDL que existen o cree archivos WSDL nuevos. Para obtener más información sobre este paso, consulte [archivos WSDL del adaptador](../core/adapter-wsdl-files.md).  
  
6. Modifique el código de ejemplo para que devuelva archivos XSD adicionales que el adaptador necesita y que no están incluidos en los archivos WSDL. Para obtener más información sobre este paso, consulte [método GetSchema del adaptador](../core/adapter-getschema-method.md).  
  
7. Modifique las claves de registro del adaptador y ejecute el archivo de Registro del adaptador. Para obtener más información sobre este paso, consulte [adaptador de archivo de registro](../core/adapter-registration-file.md).  
  
8. Instale el adaptador estático en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre este paso, consulte [instalar el adaptador en BizTalk Server](../core/install-the-adapter-into-biztalk-server.md).  
  
9. Pruebe los cambios realizados en las páginas de propiedades del adaptador. Vuelva a generar el adaptador para probar la interfaz de usuario que aparece en el Asistente para agregar metadatos de adaptador. Para obtener más información sobre este paso, consulte [compilar y probar el proyecto de adaptador](../core/build-and-test-the-adapter-project.md)  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [IStaticAdapterConfig de adaptador estático (interfaz)](../core/static-adapter-istaticadapterconfig-interface.md)  
  
-   [Categorías de esquema en el Asistente para agregar metadatos de adaptador](../core/schema-categories-in-the-add-adapter-metadata-wizard.md)
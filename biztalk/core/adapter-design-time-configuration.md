---
title: Configuración de tiempo de diseño de adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5e7b63c-6e17-4c54-9bbf-6964668a2420
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 815690aee7178db52936e8f1aca5641d1be945b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987373"
---
# <a name="adapter-design-time-configuration"></a>Configuración de adaptador en tiempo de diseño
Un adaptador contiene un componente de tiempo de ejecución y un componente de tiempo de diseño. El componente de tiempo de ejecución no está visible para el usuario. Es responsable de forma transparente para la transmisión, recepción y procesamiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mensajes.  
  
 El componente de tiempo de diseño de un adaptador se puede ver a través de las interfaces de usuario administrativas. Es responsable de mostrar las propiedades disponibles, aceptar la entrada administrativa y validar dicha entrada para configurar el adaptador. Es fundamental que el componente de tiempo de diseño permita configurar adecuadamente las propiedades del adaptador con el fin de que se habilite la funcionalidad de tiempo de ejecución necesaria para intercambiar los mensajes de forma correcta.  
  
 En esta sección solo se describe el componente de tiempo de diseño de un adaptador. Por tanto, nos centraremos principalmente en cómo ver y establecer la configuración del adaptador. Se pueden seguir dos métodos para configurar un adaptador:  
  
- **Explorador de propiedades.** Propiedades de adaptador de envío o recepción puerto o un envío o controlador de recepción, se configuran a través del menú propiedades mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Durante la configuración de estos artefactos, se selecciona el adaptador (transporte) y se configuran sus propiedades con un explorador de propiedades. Las propiedades correspondientes se muestran a través de un esquema con un nombre fijo. Por ejemplo, en el caso de un controlador de envío (transmisión), las propiedades se encontrarían en el archivo TransmitHandler.xsd; en el caso de una ubicación de recepción, las propiedades estarían en el archivo ReceiveLocation.xsd.  Implementa el adaptador el **IAdapterConfig** interfaz para buscar y cargar el esquema apropiado para exponer las propiedades específicas del explorador de propiedades. El **IAdapterConfigValidation** interfaz se usa para validar esas entradas y realizar modificaciones finales a los valores antes de guardar los datos de configuración.  
  
- **Metadatos de Asistente para agregar adaptador.** En el caso de la aplicación y los adaptadores de la base de datos, es posible que deba importar esquemas auxiliares que describan los tipos de mensaje y tipos de puerto que el adaptador necesita en el proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Asimismo, a veces es necesario consumir los servicios proporcionados por el adaptador. El Asistente para agregar metadatos de adaptador permite ver los servicios admitidos por un adaptador e importar los tipos de mensaje y puerto relacionados en el proyecto. Este proceso se denomina "recolección de metadatos". Como programador de adaptadores que cree un archivo XML que describa esos servicios y exponerlo en el Asistente en tiempo de diseño a través del **IStaticAdapterConfig** o **IDynamicAdapterConfig** interfaz, con los siguientes resultados:  
  
  -   **Adaptador estático.** el asistente proporciona una estructura jerárquica de árbol estándar predeterminada con la que mostrar los servicios del adaptador. Por adaptador estático se entiende un adaptador que usa la interfaz de usuario de árbol estándar que proporciona el asistente. Use la **IStaticAdapterConfig.GetServiceOrganization** y **GetServiceDescription** métodos para permitir que los servicios seleccionados se agregan al proyecto de BizTalk. Ésta es la opción de configuración más sencilla para un programador de adaptadores, pero el inconveniente es la rigidez del formato de presentación.  
  
  -   **Adaptador dinámico.** si la interfaz de usuario básica de selección de servicios del asistente no le ofrece la flexibilidad que necesita de una interfaz de usuario, puede crear una interfaz de usuario personalizada que el asistente muestre dinámicamente. Use la **IDynamicAdapterConfig.DisplayUI** método para mostrar la interfaz de usuario personalizada para permitir la selección de servicios que se va a agregarse a un proyecto de BizTalk.  
  
  En esta sección se proporcionan dos conjuntos de directrices para la configuración en tiempo de diseño: de forma estática y dinámica.  
  
  Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] kit de desarrollo de software (SDK) incluye un adaptador de archivo de ejemplo que puede usar como plantilla para crear y personalizar sus propias soluciones de configuración tiempo de diseño del adaptador. Los distintos temas de configuración en tiempo de diseño incluyen notas y referencias acerca del adaptador de archivo de ejemplo para ayudarle a modificar los requisitos de configuración del adaptador personalizado. Para comprender mejor estas directrices, tal vez desee instalar, compilar y ejecutar el adaptador de archivo de ejemplo proporcionado en el SDK. Consulte [(ejemplo de BizTalk Server) del adaptador de archivo](../core/file-adapter-biztalk-server-sample.md) para obtener más información.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración estática de adaptadores en tiempo de diseño](../core/static-design-time-adapter-configuration.md)  
  
-   [Configuración dinámica de adaptadores en tiempo de diseño](../core/dynamic-design-time-adapter-configuration.md)  
  
-   [Esquemas de configuración de adaptadores](../core/adapter-configuration-schemas.md)  
  
-   [Archivos WSDL del adaptador](../core/adapter-wsdl-files.md)  
  
-   [Método GetSchema del adaptador](../core/adapter-getschema-method.md)  
  
-   [Archivo de registro del adaptador](../core/adapter-registration-file.md)  
  
-   [Instalar el adaptador en BizTalk Server](../core/install-the-adapter-into-biztalk-server.md)  
  
-   [Generar y probar el proyecto de adaptador](../core/build-and-test-the-adapter-project.md)
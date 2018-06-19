---
title: Implementación de aplicaciones y dependencias | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], dependencies
- assemblies, dependencies
- artifacts, dependencies
- applications, dependencies
ms.assetid: b78c5a0d-b042-4862-bce7-59469365b369
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc7e4b44a09da04e62062d90cd99da0354cca34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242212"
---
# <a name="dependencies-and-application-deployment"></a>Dependencias e implementación de aplicaciones
En este tema se describe cómo influyen las dependencias entre artefactos de dos o más aplicaciones de BizTalk en la implementación y el mantenimiento de las aplicaciones.  
  
 Cuando un artefacto necesita usar otro artefacto para funcionar correctamente, se dice que *dependientes* en otro artefacto. Un ejemplo de tal dependencia es cuando una orquestación necesita usar un esquema específico para la resolución de mensajes o una canalización específica para transmitir mensajes correctamente. En ambos escenarios, la orquestación es dependiente de otro artefacto.  
  
 Antes de poder actualizar un artefacto en una aplicación, en primer lugar, debe anular su implementación, junto con los artefactos que dependen de ella. Cuando existen artefactos con dependencias en la misma aplicación, BizTalk Server controla de forma automática las tareas de anulación de la implementación y de nueva implementación para los artefactos actualizados y dependientes. Cuando los artefactos que tienen dependencias se encuentran en distintas aplicaciones, aunque este no sea el caso. Debe seguir pasos manuales para anular la implementación de los artefactos con dependencias antes de poder actualizar un artefacto del que dependen. Después, debe volver a implementar los artefactos dependientes.  
  
 Para evitar seguir estos pasos manuales cuando desee actualizar un artefacto del que dependen otros artefactos, puede intentar mantener todos los artefactos con dependencias juntos en la misma aplicación. Sin embargo, esto no es posible. Como se describe en [artefactos que deben ser únicos en una aplicación o un grupo de](../core/artifacts-that-must-be-unique-in-an-application-or-group.md), la mayoría de los tipos de artefactos deben ser únicos en un grupo de BizTalk. No puede tener el mismo artefacto en dos aplicaciones distintas del mismo grupo, incluso cuando ambas aplicaciones contienen artefactos que dependen del mismo artefacto.  
  
 Cuando sucede esto, puede agregar el artefacto necesario a una aplicación y, a continuación, agregar una referencia a dicha aplicación desde otras aplicaciones que contengan artefactos que dependen de ella. Si se agrega una referencia a una aplicación, los artefactos de la aplicación pueden usar los artefactos de la aplicación a la que hace referencia. Para obtener instrucciones sobre cómo agregar una referencia, vea [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md).  
  
 El siguiente diagrama muestra dos aplicaciones que dependen de artefactos de una tercera aplicación. La aplicación de procesamiento de pedidos usa Schema1, que se incluye en la aplicación de esquemas, de modo que la aplicación de procesamiento de pedidos contiene una referencia a la aplicación de esquemas. La aplicación de hipotecas usa Schema2, que también se incluye en la aplicación de esquemas y, al igual que la aplicación anterior, contiene una referencia a la última.  
  
 ![Dos aplicaciones hacen referencia a una tercera aplicación](../core/media/applicationdependencies.gif "ApplicationDependencies")  
  
 Agregar una referencia de una aplicación a otra crea una dependencia entre las dos aplicaciones que influyen en cómo implementar y administrar ambas aplicaciones. Debido a varios efectos de dependencias de aplicaciones se describe más adelante en este tema, se recomienda que siga las prácticas recomendadas para agregar artefactos a la aplicación, como se describe en [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
 El siguiente diagrama ilustra los pasos implicados en la actualización de un ensamblado cuando hay una cadena de dependencia y todos los ensamblados que dependen del ensamblado que se va a actualizar se encuentran en la misma aplicación.  
  
 ![Actualizar un ensamblado con dependencias](../core/media/simpleadminredeploy.gif "SimpleAdminRedeploy")  
  
 El siguiente diagrama ilustra los pasos implicados en la actualización de un ensamblado cuando hay una cadena de dependencias en el ensamblado que se va a actualizar y uno de los ensamblados dependientes se encuentra en una aplicación distinta.  
  
 ![Actualizar un ensamblado con dependencias externas](../core/media/complexadminredeploy.gif "ComplexAdminRedeploy")  
  
> [!NOTE]
>  El motivo por el que se realiza una detención completa antes de actualizar un ensamblado, es que hacerlo de forma automática da de baja la orquestación, detiene y finaliza todos los mensajes. Si es necesario continuar con el procesamiento de mensajes, puede implementar una versión diferente del mismo ensamblado y, por tanto, evitar la detención y finalización de los mensajes. Para obtener más información, consulte [actualizar aplicaciones de BizTalk](../core/updating-biztalk-applications.md).  
  
 Los siguientes efectos pueden derivar de dependencias entre aplicaciones:  
  
-   **Detención de un artefacto.** Si detiene un artefacto en una aplicación (que puede derivar de la detención de la aplicación completa) de la que depende otra aplicación, la aplicación dependiente no funcionará correctamente. Para obtener más información acerca de cómo detener una aplicación, consulte [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md).  
  
-   **Quitar o cambiar el estado de un artefacto.** Cuando agrega una referencia de una aplicación a otra y realiza cambios en el estado de un artefacto del que depende otra aplicación o quita el artefacto, la aplicación con dependencia no funcionará correctamente. Para obtener más información acerca de cómo cambiar el estado de un artefacto, consulte la sección del artefacto correspondiente en [administrar artefactos](../core/managing-artifacts.md).  
  
-   **Importación de aplicaciones que tienen dependencias.** Si desea importar una aplicación en un grupo de BizTalk diferente y ejecutarla en dicho grupo, debe importar los artefactos de los que depende esta aplicación. Puede hacerlo mediante la importación, en primer lugar, de otra aplicación o mediante la agregación del artefacto necesario a la aplicación que lo requiere. Para obtener más información acerca de cómo importar aplicaciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
    > [!NOTE]
    >  BizTalk Server comprueba la identidad de una aplicación mediante la correspondencia de los nombres de la aplicación en el grupo de BizTalk de origen y de destino. No comprueba que los artefactos de los que depende la aplicación se incluyen en ella. Al importar una aplicación con dependencias y la aplicación a la que se hace referencia, se recomienda comprobar que la aplicación a la que se hace referencia contiene los artefactos necesarios.  
  
-   **Importación de aplicaciones que tienen referencias.** Si una aplicación que se importa depende de un artefacto de otra aplicación, es posible que se deba agregar una referencia a esta aplicación. El Asistente para importación proporciona esta opción. Si usa el comando ImportApp de BTSTask, sin embargo, debe agregar la referencia a la aplicación después de la importación, como se describe en [cómo agregar una referencia a otra aplicación](../core/how-to-add-a-reference-to-another-application.md). Mientras que BizTalk Server comprueba que la aplicación a la que se hace referencia existe, se recomienda seguir los pasos adicionales para comprobar que la aplicación a la que se hace referencia contiene el artefacto necesario.  
  
-   **Instalación de aplicaciones que tienen dependencias.** Cuando instala una aplicación, debe instalar también las aplicaciones de las que depende. Cuando instale una aplicación que tenga dependencia de un artefacto, como de un ensamblado de BizTalk, que está contenido en otra aplicación, también es necesario instalar primero la aplicación que contiene el artefacto. Por ejemplo, si desea instalar la aplicación A y ésta depende de un ensamblado de la aplicación B, debe instalar primer la aplicación B. A continuación, puede instalar a aplicación. Para obtener más información acerca de cómo instalar aplicaciones, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
-   **Mover un artefacto.** Cuando mueve un artefacto a una aplicación nueva, se mueven también los artefactos con los que tiene relaciones de dependencia a no ser que la aplicación nueva tenga una referencia a las aplicaciones que contienen los artefactos de los que depende el artefacto movido. Además, los artefactos que tienen dependencias en el artefacto movido también se moverán a menos que las aplicaciones que los contienen tengan una referencia a la nueva aplicación. Al mover un artefacto, aparecerá la lista de los otros artefactos que también se moverán. Para obtener instrucciones acerca de cómo mover un artefacto, consulte [cómo mover un artefacto a una aplicación diferente](../core/how-to-move-an-artifact-to-a-different-application.md).  
  
-   **Actualizar un artefacto cuando un artefacto de otra aplicación depende de ella.** Cuando actualiza un artefacto de una aplicación con dependencia de un artefacto en la misma aplicación, BizTalk Server se encarga de forma automática de la anulación de la implementación y de la nueva implementación del artefacto dependiente. Si desea actualizar un artefacto en una aplicación, así como un artefacto de otra aplicación dependiente de ella, debe anular la implementación y volver a implementar el artefacto dependiente de forma manual de la siguiente manera:  
  
    1.  Detenga, dé de baja y desenlace el artefacto dependiente.  
  
    2.  Actualice el artefacto del que depende.  
  
    3.  Enlace, dé de alta e iniciar el artefacto dependiente.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)
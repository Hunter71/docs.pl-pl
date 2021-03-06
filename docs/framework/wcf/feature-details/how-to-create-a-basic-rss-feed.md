---
title: 'Instrukcje: Tworzenie podstawowego kanału informacyjnego RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: d5b62d968c38401a19fc9009954450bef210e5a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-basic-rss-feed"></a>Instrukcje: Tworzenie podstawowego kanału informacyjnego RSS
Windows Communication Foundation (WCF) służy do tworzenia usługi, który ujawnia zespolonego źródła danych. W tym temacie omówiono sposób tworzenia usługa syndykacji ujawniający źródła zespolonego RSS.  
  
### <a name="to-create-a-basic-syndication-service"></a>Aby utworzyć usługę zespolonego podstawowe  
  
1.  Definiowanie kontraktu usługi przy użyciu interfejsu oznaczony atrybutem <xref:System.ServiceModel.Web.WebGetAttribute> atrybutu. Każda operacja uwidocznioną jak zespolonego źródła powinna zwrócić <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> obiektu.  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    >  Wszystkie operacje usługi, które są stosowane <xref:System.ServiceModel.Web.WebGetAttribute> atrybutu są mapowane na żądania HTTP GET. Aby mapować operację na innej metody HTTP, należy użyć <xref:System.ServiceModel.Web.WebInvokeAttribute> zamiast tego. Aby uzyskać więcej informacji, zobacz [porady: Tworzenie podstawowej usługi HTTP sieci Web WCF](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md).  
  
2.  Implementowanie kontraktu usługi.  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3.  Utwórz <xref:System.ServiceModel.Syndication.SyndicationFeed> obiektu i dodać autora, kategoria i opis.  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4.  Utwórz kilka <xref:System.ServiceModel.Syndication.SyndicationItem> obiektów.  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5.  Dodaj <xref:System.ServiceModel.Syndication.SyndicationItem> do źródła danych.  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6.  Zwróć kanału informacyjnego.  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a>Do hosta usługi  
  
1.  Tworzy obiekt <xref:System.ServiceModel.Web.WebServiceHost>.  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2.  Otworzyć hosta usługi i poczekaj, aż użytkownik naciśnie klawisz ENTER.  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a>Aby wywołać GetBlog() z HTTP GET  
  
1.  Otwórz program Internet Explorer, wpisz następujący adres URL, a następnie naciśnij klawisz ENTER: http://localhost:8000/BlogService/GetBlog. Adres URL zawiera adres podstawowy usługi (http://localhost:8000/BlogService), względny adres punktu końcowego i do wywołania operacji usługi.  
  
### <a name="to-call-getblog-from-code"></a>Aby wywołać GetBlog() z kodu  
  
1.  Utwórz <xref:System.Xml.XmlReader> z adresu podstawowego i wywoływania metody.  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2.  Wywołaj statycznych <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> metody, przekazując <xref:System.Xml.XmlReader> właśnie utworzony.  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     To wywołanie operacji usługi i wypełnia nowy <xref:System.ServiceModel.Syndication.SyndicationFeed> z elementem formatującym zwrócony przez operację usługi.  
  
3.  Dostęp do źródła strumieniowego obiektu.  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a>Przykład  
 Poniżej znajduje się pełna listy w tym przykładzie kodu.  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 W przypadku kompilowania kodu poprzedni kod, odniesienia System.ServiceModel.dll i System.ServiceModel.Web.dll.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.ServiceModel.WebHttpBinding>  
 <xref:System.ServiceModel.Web.WebGetAttribute>

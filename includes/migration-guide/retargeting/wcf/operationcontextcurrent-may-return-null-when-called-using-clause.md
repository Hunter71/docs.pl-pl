### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>Obiekt OperationContext.Current może zwrócić wartość null, gdy wywoływana w przy użyciu klauzuli

|   |   |
|---|---|
|Szczegóły|<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> może zwrócić <code>null</code> i <xref:System.NullReferenceException> może spowodować, jeśli spełnione są wszystkie poniższe warunki:<ul><li>Możesz pobrać wartość <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> właściwość w metodę, która zwraca <xref:System.Threading.Tasks.Task> lub <xref:System.Threading.Tasks.Task%601>.</li><li>Można utworzyć wystąpienia <xref:System.ServiceModel.OperationContextScope> obiektu w <code>using</code> klauzuli.</li><li>Możesz pobrać wartość <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> właściwości <code>using statement</code>. Na przykład:</li></ul><pre><code class="language-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|Sugestia|Aby rozwiązać ten problem, można wykonać następujące czynności:<ul><li>Ten kod w następujący sposób, aby utworzyć obiekt klasy zmodyfikować inną niż<code>null</code> <xref:System.ServiceModel.OperationContext.Current%2A> obiektu:</li></ul><pre><code class="language-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>Zainstaluj najnowszą aktualizację programu .NET Framework 4.6.2, lub Uaktualnij do nowszej wersji programu .NET Framework. Powoduje wyłączenie przepływ <xref:System.Threading.ExecutionContext> w <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> i przywrócenie zachowania aplikacji WCF w programie .NET Framework 4.6.1 i wcześniejszych wersjach. To zachowanie jest konfigurowalne; odpowiada to dodanie następującego ustawienia app do pliku konfiguracji:</li></ul><pre><code class="language-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Jeśli ta zmiana jest niepożądane, aplikacja jest zależna od kontekstu wykonywania przechodzenia między kontekstami operacji przepływ można włączyć w następujący sposób:<pre><code class="language-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Zakres|Krawędź|
|Wersja|4.6.2|
|Typ|Przekierowania|
|Dotyczy interfejsów API|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|

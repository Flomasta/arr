# arr
<script src="clipboard.min.js"></script>

<?php
$_POST['more'];
$more = $_POST['more'];
     if ($more[0]=='') {
                echo "Введите данные:";
    }

else
            {    echo '<textarea cols ="100" rows ="20" id="textarea-example">';

                $str = preg_match_all('/([0-9]{9})[^0-9]+([0-9]{3,4})/', $more[0],$b);

                $header = htmlspecialchars('h2. Изменить сумму списания.
            ');
                $header2 = htmlspecialchars('|\2=.<pre>
            ');

                echo $header;
                echo $header2;



                for ($i = 0; $i < count($b[2]); $i++) {

            echo "UPDATE pending_rebills SET rebill_price = " . $b[2][$i] .  " WHERE init_transaction_id IN (" . $b[1][$i]  . ");
            ";
                
}


$footer = htmlspecialchars('</pre>|
');
$footer2 = htmlspecialchars('|Отметка о исполнении||');
echo $footer;
echo $footer2
;
echo "</textarea>";
echo "<br/>";
echo '<button class="btn-clipboard" data-clipboard-target="#textarea-example">Скопировать в буфер обмена</button>';
}

?>
<br/>

<script>
new Clipboard('.btn-clipboard'); // Не забываем инициализировать библиотеку на нашей кнопке
</script>
<br/>
<form action="testar.php" method="post">
     <textarea  rows ="30"  name="more[]"></textarea>
     <br/>
    <input type="submit" value="Вжух!"></input>

</form>

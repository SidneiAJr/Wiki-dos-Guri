# Exemplo de Codigo para Java - Android Studio | Calculadora de Cosumo W



```Java
  EditText editText1 = findViewById(R.id.ed_mem);
        EditText editText2 = findViewById(R.id.ed_hd);
        EditText editText3 = findViewById(R.id.ed_proce);
        EditText editText4 = findViewById(R.id.ed_ssd);
        EditText editText6 = findViewById(R.id.ed_nve);
        EditText editText7 = findViewById(R.id.ed_placa);
        Button buttoncalcular = findViewById(R.id.btn_consumo2);
        TextView textViewsaida = findViewById(R.id.txt_totalw);
        TextView textViewsaida2 = findViewById(R.id.txt_totalw2);


        buttoncalcular.setOnClickListener(v->{
            String men = editText1.getText().toString();
            String hd = editText2.getText().toString();
            String pro = editText3.getText().toString();
            String ssd = editText4.getText().toString();
            String nve = editText6.getText().toString();
            String placa = editText7.getText().toString();

            if(!men.isEmpty()&&!hd.isEmpty()&&!pro.isEmpty()&&!ssd.isEmpty()&&!nve.isEmpty()&&!placa.isEmpty()){
                int memoria = Integer.parseInt(men);
                int processador = Integer.parseInt(pro);
                int placavideo = Integer.parseInt(placa);
                int ssd2 = Integer.parseInt(ssd);
                int nve2 = Integer.parseInt(nve);
                int hd2 = Integer.parseInt(hd);
                int res = (memoria+processador+placavideo+ssd2+nve2+hd2);
                double potencia = res*0.30;
                double potenciatotal = res + potencia;
                textViewsaida2.setText("Potencia da Fonte Total "+ potenciatotal);
                if(res<=600){
                 textViewsaida.setText("Fonte 600W ou Maior");
                }else{
                    textViewsaida.setText("Potencia da Fonte Recomendada 500W ou menor");
                }
            }
        });
```

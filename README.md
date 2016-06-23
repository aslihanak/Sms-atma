# Sms-atma
package com.example.asus.applicationsms;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
//import android.telephony.SmsManager;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        final EditText telNo = (EditText)findViewById(R.id.etTelNo);
        final EditText mesaj = (EditText)findViewById(R.id.etMesaj);
        Button gonder = (Button)findViewById(R.id.button);

       // android.telephony.SmsManager sms = android.telephony.SmsManager.getDefault();
      //  sms.sendTextMessage("05064301176", null, "Mesaj", null, null);

        gonder.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {

                android.telephony.SmsManager mng = android.telephony.SmsManager.getDefault();

                mng.sendTextMessage(telNo.getText().toString(),null,mesaj.getText().toString(),null,null);


            }
        });
    }
}

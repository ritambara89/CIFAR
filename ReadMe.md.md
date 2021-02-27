1) Final Validation accuracy for Base Network: 81.65

2) Model defination:
model = Sequential()
model.add(SeparableConv2D(64, 3, 3, input_shape=(32, 32, 3)))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(64, 3, 3))
model.add(SeparableConv2D(128, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(128, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(256, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(MaxPooling2D(pool_size=(2,2)))
model.add(Dropout(0.1))

model.add(SeparableConv2D(256, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(64, 1, 1))


model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(128, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(256, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(SeparableConv2D(64, 1, 1))
model.add(SeparableConv2D(64, 3, 3))
model.add(BatchNormalization())
model.add(Activation('relu'))
model.add(Dropout(0.1))

model.add(Flatten())
model.add(Dense(64))
model.add(Activation('relu'))
model.add(Dropout(0.1))
model.add(Dense(128))
model.add(Activation('relu'))
# model.add(Dropout(0.1))
model.add(Dense(num_classes, activation='softmax'))

model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
model.summary()

3) 50 epoch logs
Epoch 1/50
390/390 [==============================] - 97s 250ms/step - loss: 1.6984 - acc: 0.3641 - val_loss: 1.6567 - val_acc: 0.4209
Epoch 2/50
390/390 [==============================] - 89s 229ms/step - loss: 1.2794 - acc: 0.5378 - val_loss: 1.5333 - val_acc: 0.5064
Epoch 3/50
390/390 [==============================] - 89s 229ms/step - loss: 1.1044 - acc: 0.6051 - val_loss: 1.1307 - val_acc: 0.5955
Epoch 4/50
390/390 [==============================] - 89s 228ms/step - loss: 0.9967 - acc: 0.6474 - val_loss: 1.0649 - val_acc: 0.6397
Epoch 5/50
390/390 [==============================] - 89s 228ms/step - loss: 0.9112 - acc: 0.6777 - val_loss: 0.9857 - val_acc: 0.6617
Epoch 6/50
390/390 [==============================] - 89s 228ms/step - loss: 0.8408 - acc: 0.7041 - val_loss: 0.9738 - val_acc: 0.6698
Epoch 7/50
390/390 [==============================] - 89s 228ms/step - loss: 0.7856 - acc: 0.7244 - val_loss: 0.9581 - val_acc: 0.6757
Epoch 8/50
390/390 [==============================] - 89s 228ms/step - loss: 0.7371 - acc: 0.7409 - val_loss: 1.0149 - val_acc: 0.6729
Epoch 9/50
390/390 [==============================] - 89s 228ms/step - loss: 0.7019 - acc: 0.7536 - val_loss: 0.8159 - val_acc: 0.7193
Epoch 10/50
390/390 [==============================] - 89s 228ms/step - loss: 0.6722 - acc: 0.7647 - val_loss: 0.7200 - val_acc: 0.7575
Epoch 11/50
390/390 [==============================] - 89s 228ms/step - loss: 0.6381 - acc: 0.7788 - val_loss: 0.8130 - val_acc: 0.7250
Epoch 12/50
390/390 [==============================] - 89s 228ms/step - loss: 0.6126 - acc: 0.7878 - val_loss: 0.7313 - val_acc: 0.7517
Epoch 13/50
390/390 [==============================] - 89s 228ms/step - loss: 0.5879 - acc: 0.7949 - val_loss: 0.7018 - val_acc: 0.7640
Epoch 14/50
390/390 [==============================] - 89s 228ms/step - loss: 0.5664 - acc: 0.8034 - val_loss: 0.6735 - val_acc: 0.7722
Epoch 15/50
390/390 [==============================] - 89s 229ms/step - loss: 0.5430 - acc: 0.8106 - val_loss: 0.7108 - val_acc: 0.7701
Epoch 16/50
390/390 [==============================] - 89s 229ms/step - loss: 0.5208 - acc: 0.8179 - val_loss: 0.7030 - val_acc: 0.7666
Epoch 17/50
390/390 [==============================] - 89s 228ms/step - loss: 0.5049 - acc: 0.8255 - val_loss: 0.6839 - val_acc: 0.7750
Epoch 18/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4846 - acc: 0.8303 - val_loss: 0.6881 - val_acc: 0.7706
Epoch 19/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4638 - acc: 0.8389 - val_loss: 0.7038 - val_acc: 0.7771
Epoch 20/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4618 - acc: 0.8409 - val_loss: 0.6721 - val_acc: 0.7789
Epoch 21/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4358 - acc: 0.8485 - val_loss: 0.7524 - val_acc: 0.7574
Epoch 22/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4288 - acc: 0.8500 - val_loss: 0.7077 - val_acc: 0.7758
Epoch 23/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4172 - acc: 0.8549 - val_loss: 0.6321 - val_acc: 0.7940
Epoch 24/50
390/390 [==============================] - 89s 228ms/step - loss: 0.4057 - acc: 0.8571 - val_loss: 0.6924 - val_acc: 0.7865
Epoch 25/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3908 - acc: 0.8644 - val_loss: 0.7703 - val_acc: 0.7668
Epoch 26/50
390/390 [==============================] - 89s 227ms/step - loss: 0.3863 - acc: 0.8654 - val_loss: 0.7224 - val_acc: 0.7778
Epoch 27/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3710 - acc: 0.8691 - val_loss: 0.6498 - val_acc: 0.7941
Epoch 28/50
390/390 [==============================] - 89s 227ms/step - loss: 0.3666 - acc: 0.8725 - val_loss: 0.6639 - val_acc: 0.7904
Epoch 29/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3520 - acc: 0.8771 - val_loss: 0.7282 - val_acc: 0.7758
Epoch 30/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3533 - acc: 0.8757 - val_loss: 0.6667 - val_acc: 0.7895
Epoch 31/50
390/390 [==============================] - 89s 227ms/step - loss: 0.3382 - acc: 0.8812 - val_loss: 0.7216 - val_acc: 0.7857
Epoch 32/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3308 - acc: 0.8834 - val_loss: 0.6565 - val_acc: 0.7989
Epoch 33/50
390/390 [==============================] - 89s 227ms/step - loss: 0.3225 - acc: 0.8862 - val_loss: 0.7115 - val_acc: 0.7951
Epoch 34/50
390/390 [==============================] - 89s 228ms/step - loss: 0.3134 - acc: 0.8907 - val_loss: 0.6287 - val_acc: 0.8089
Epoch 35/50
390/390 [==============================] - 89s 227ms/step - loss: 0.3123 - acc: 0.8908 - val_loss: 0.6526 - val_acc: 0.8033
Epoch 36/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2999 - acc: 0.8946 - val_loss: 0.6721 - val_acc: 0.7955
Epoch 37/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2946 - acc: 0.8971 - val_loss: 0.6696 - val_acc: 0.8005
Epoch 38/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2939 - acc: 0.8966 - val_loss: 0.7019 - val_acc: 0.7936
Epoch 39/50
390/390 [==============================] - 89s 229ms/step - loss: 0.2807 - acc: 0.9012 - val_loss: 0.7266 - val_acc: 0.7893
Epoch 40/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2741 - acc: 0.9044 - val_loss: 0.6793 - val_acc: 0.7983
Epoch 41/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2696 - acc: 0.9052 - val_loss: 0.6641 - val_acc: 0.8042
Epoch 42/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2653 - acc: 0.9071 - val_loss: 0.7604 - val_acc: 0.7863
Epoch 43/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2614 - acc: 0.9084 - val_loss: 0.6556 - val_acc: 0.8114
Epoch 44/50
390/390 [==============================] - 89s 227ms/step - loss: 0.2555 - acc: 0.9110 - val_loss: 0.6229 - val_acc: 0.8169
Epoch 45/50
390/390 [==============================] - 89s 227ms/step - loss: 0.2512 - acc: 0.9124 - val_loss: 0.6640 - val_acc: 0.8115
Epoch 46/50
390/390 [==============================] - 89s 227ms/step - loss: 0.2509 - acc: 0.9116 - val_loss: 0.8293 - val_acc: 0.7719
Epoch 47/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2429 - acc: 0.9150 - val_loss: 0.6773 - val_acc: 0.8095
Epoch 48/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2381 - acc: 0.9163 - val_loss: 0.6848 - val_acc: 0.8097
Epoch 49/50
390/390 [==============================] - 89s 228ms/step - loss: 0.2333 - acc: 0.9181 - val_loss: 0.7582 - val_acc: 0.7928
Epoch 50/50
390/390 [==============================] - 89s 227ms/step - loss: 0.2327 - acc: 0.9189 - val_loss: 0.6598 - val_acc: 0.8165
Model took 4456.07 seconds to train

summary(model[0], input_size=(16,2))
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Linear-1                 [-1, 1024]          33,792
       BatchNorm1d-2                 [-1, 1024]           2,048
              Mish-3                 [-1, 1024]               0
           Dropout-4                 [-1, 1024]               0
            Linear-5                 [-1, 1024]       1,048,576
       BatchNorm1d-6                 [-1, 1024]           2,048
              Mish-7                 [-1, 1024]               0
           Dropout-8                 [-1, 1024]               0
              LBAD-9                 [-1, 1024]               0
           Linear-10                 [-1, 1024]       1,048,576
      BatchNorm1d-11                 [-1, 1024]           2,048
             Mish-12                 [-1, 1024]               0
          Dropout-13                 [-1, 1024]               0
             LBAD-14                 [-1, 1024]               0
           Linear-15                   [-1, 51]          52,275
           Linear-16                   [-1, 51]          52,275
================================================================
Total params: 2,241,638
Trainable params: 2,241,638
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 0.11
Params size (MB): 8.55
Estimated Total Size (MB): 8.66
----------------------------------------------------------------
None





summary(model[1], input_size=(2560,51))
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Linear-1                 [-1, 1024]          53,248
       BatchNorm1d-2                 [-1, 1024]           2,048
              Mish-3                 [-1, 1024]               0
           Dropout-4                 [-1, 1024]               0
            Linear-5                 [-1, 1024]       1,048,576
       BatchNorm1d-6                 [-1, 1024]           2,048
              Mish-7                 [-1, 1024]               0
           Dropout-8                 [-1, 1024]               0
              LBAD-9                 [-1, 1024]               0
           Linear-10                 [-1, 1024]       1,048,576
      BatchNorm1d-11                 [-1, 1024]           2,048
             Mish-12                 [-1, 1024]               0
          Dropout-13                 [-1, 1024]               0
             LBAD-14                 [-1, 1024]               0
           Linear-15                   [-1, 48]          49,200
             Tanh-16                   [-1, 48]               0
================================================================
Total params: 2,205,744
Trainable params: 2,205,744
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.50
Forward/backward pass size (MB): 0.11
Params size (MB): 8.41
Estimated Total Size (MB): 9.02
----------------------------------------------------------------
None



summary(model[2], input_size=(16,2))
----------------------------------------------------------------
        Layer (type)               Output Shape         Param #
================================================================
            Linear-1                 [-1, 1024]          33,792
         LeakyReLU-2                 [-1, 1024]               0
            Linear-3                 [-1, 1024]       1,049,600
         LeakyReLU-4                 [-1, 1024]               0
           Dropout-5                 [-1, 1024]               0
              LBAD-6                 [-1, 1024]               0
            Linear-7                 [-1, 1024]       1,049,600
         LeakyReLU-8                 [-1, 1024]               0
           Dropout-9                 [-1, 1024]               0
             LBAD-10                 [-1, 1024]               0
           Linear-11                 [-1, 1024]       1,049,600
        LeakyReLU-12                 [-1, 1024]               0
          Dropout-13                 [-1, 1024]               0
             LBAD-14                 [-1, 1024]               0
           Linear-15                 [-1, 1024]       1,049,600
        LeakyReLU-16                 [-1, 1024]               0
          Dropout-17                 [-1, 1024]               0
             LBAD-18                 [-1, 1024]               0
           Linear-19                    [-1, 1]           1,025
          Sigmoid-20                    [-1, 1]               0
================================================================
Total params: 4,233,217
Trainable params: 4,233,217
Non-trainable params: 0
----------------------------------------------------------------
Input size (MB): 0.00
Forward/backward pass size (MB): 0.14
Params size (MB): 16.15
Estimated Total Size (MB): 16.29
----------------------------------------------------------------
None







\begin{center}
    \begin{tabular}{ p{0.2\textwidth}| p{0.7\textwidth}| p{0.1\textwidth}}

        \textbf{Layer Type)} & \textbf{Output Shape}                                   & \textbf{Parameters} \\
        \hline

        (0):                 & Linear(in features=32, out features=1024, bias=True)    & 33792               \\
        (1):                 & BatchNorm1d(1024, eps=1e-05, momentum=0.1)              & 2048                \\
        (2):                 & Mish()                                                  & 0                   \\
        (3):                 & Dropout(p=0.2, inplace=False)                           & 0                   \\

        (LBAD 1):            & LBAD(                                                   &                     \\

        (w1):                & Linear(in features=1024, out features=1024, bias=False) & 1048576             \\
        (bn1):               & BatchNorm1d(1024, eps=1e-05, momentum=0.1)              & 2048                \\
        (activ):             & Mish()                                                  & 0                   \\
        (dropout):           & Dropout(p=0.2, inplace=False)                           & 0                   \\

        (LBAD 2):            & LBAD(                                                   &                     \\

        (w1):                & Linear(in features=1024, out features=1024, bias=False) & 1048576             \\
        (bn1):               & BatchNorm1d(1024, eps=1e-05, momentum=0.1)              & 2048                \\
        (activ):             & Mish()                                                  & 0                   \\
        (dropout):           & Dropout(p=0.2, inplace=False)                           & 0                   \\

        (downsample):        & LBAD(                                                   &                     \\

        (fc mean):           & Linear(in features=1024, out features=51, bias=True)    & 52275               \\
        (fc logvar):         & Linear(in features=1024, out features=51, bias=True)    & 52275               \\
    \end{tabular}
\end{center}

\begin{center}
    \begin{tabular}{ p{0.2\textwidth}| p{0.7\textwidth}| p{0.1\textwidth}}

        \textbf{Layer Type)} & \textbf{Output Shape}                                                             & \textbf{Parameters} \\
        \hline

        (0):                 & Linear(in features=51, out features=1024, bias=True)                              & 53248               \\
        (1):                 & BatchNorm1d(1024, eps=1e-05, momentum=0.1, affine=True, track running stats=True) & 2048                \\
        (2):                 & Mish()                                                                            & 0                   \\
        (3):                 & Dropout(p=0.2, inplace=False)                                                     & 0                   \\

        (LBAD 1):            & LBAD(                                                                             &                     \\
        (w1):                & Linear(in features=1024, out features=1024, bias=False)                           & 1048576             \\
        (bn1):               & BatchNorm1d(1024, eps=1e-05, momentum=0.1, affine=True, track running stats=True) & 2048                \\
        (activ):             & Mish()                                                                            & 0                   \\
        (dropout):           & Dropout(p=0.2, inplace=False)                                                     & 0                   \\

        (LBAD 2):            & LBAD(                                                                             & 0                   \\
        (w1):                & Linear(in features=1024, out features=1024, bias=False)                           & 1048576             \\
        (bn1):               & BatchNorm1d(1024, eps=1e-05, momentum=0.1, affine=True, track running stats=True) & 2048                \\
        (activ):             & Mish()                                                                            & 0                   \\
        (dropout):           & Dropout(p=0.2, inplace=False)                                                     & 0                   \\

        (dec out block):     & Sequential(                                                                       & 0                   \\
        (0):                 & Linear(in features=1024, out features=48, bias=True)                              & 49200               \\
        (1):                 & Tanh()                                                                            & 0                   \\
    \end{tabular}
\end{center}





\begin{center}
    \begin{tabular}{ p{0.2\textwidth}| p{0.7\textwidth}| p{0.1\textwidth}}

        \textbf{Layer Type)} & \textbf{Output Shape}                                  & \textbf{Parameters} \\
        \hline


        (0):                 & Linear(in features=32, out features=1024, bias=True)   & 33792               \\
        (1):                 & LeakyReLU(negative slope=0.01)                         & 0                   \\

        (LBAD 1):            & LBAD(                                                  &                     \\
        (w1):                & Linear(in features=1024, out features=1024, bias=True) & 1049600             \\
        (activ):             & LeakyReLU(negative slope=0.01)                         & 0                   \\
        (dropout):           & Dropout(p=0.5, inplace=False)                          & 0                   \\

        (LBAD 2):            & LBAD(                                                  & 0                   \\
        (w1):                & Linear(in features=1024, out features=1024, bias=True) & 1049600             \\
        (activ):             & LeakyReLU(negative slope=0.01)                         & 0                   \\
        (dropout):           & Dropout(p=0.5, inplace=False)                          & 0                   \\

        (LBAD 3):            & LBAD(                                                  & 0                   \\
        (w1):                & Linear(in features=1024, out features=1024, bias=True) & 1049600             \\
        (activ):             & LeakyReLU(negative slope=0.01)                         & 0                   \\
        (dropout):           & Dropout(p=0.5, inplace=False)                          & 0                   \\

        (LBAD 4):            & LBAD(                                                  & 0                   \\
        (w1):                & Linear(in features=1024, out features=1024, bias=True) & 1049600             \\
        (activ):             & LeakyReLU(negative slope=0.01)                         & 0                   \\
        (dropout):           & Dropout(p=0.5, inplace=False)                          & 0                   \\

        (out block):         & Sequential(                                            & 0                   \\
        (0):                 & Linear(in features=1024, out features=1, bias=True)    & 1025                \\
        (1):                 & Sigmoid()                                              & 0                   \\
    \end{tabular}
\end{center}
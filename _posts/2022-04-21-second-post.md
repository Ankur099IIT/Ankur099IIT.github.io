{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "Introduction to Tensorflow for AI, ML and DS_Hello world code.ipynb",
      "provenance": [],
      "collapsed_sections": [],
      "authorship_tag": "ABX9TyNbybB/cUmO05wMCdIQK5ng",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    },
    "accelerator": "GPU"
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/Ankur099IIT/Ankur099IIT.github.io/blob/master/Introduction_to_Tensorflow_for_AI%2C_ML_and_DS_Hello_world_code.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": 1,
      "metadata": {
        "id": "WuRCTWCeBIS1"
      },
      "outputs": [],
      "source": [
        "import numpy as np\n",
        "import tensorflow as tf"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "Dense means one layer and \n",
        "units = 1 means one neuron\n",
        "\n",
        "Sequential means layers are used in sequence one after the other."
      ],
      "metadata": {
        "id": "E7FZCCbpW5fN"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "model = tf.keras.Sequential([\n",
        "        tf.keras.layers.Dense(units = 1, input_shape = [1])                     \n",
        "])\n",
        "\n",
        "model.compile(\n",
        "    loss = tf.keras.losses.MAE,\n",
        "    optimizer = tf.keras.optimizers.SGD(),\n",
        "    metrics = ['mse']\n",
        ")\n",
        "\n",
        "X = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0])\n",
        "y = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 7.0])\n",
        "\n",
        "model.fit(X, y, epochs = 500, verbose = 0) "
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "ZbMfBfnzR-hX",
        "outputId": "8eaf2eb8-6078-4bda-a16c-e8feedafa1d9"
      },
      "execution_count": 14,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<keras.callbacks.History at 0x7f16101cef10>"
            ]
          },
          "metadata": {},
          "execution_count": 14
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "during each epoch what happens is, our model guess a relation/patter between X and y, then the loss function is used to check how wrong the guess is with the ground truth/actual value, then optimizer improves the guess. This is called one epoch.\n",
        "\n",
        "Lower loss function means the model is closer to find the relation between X and y."
      ],
      "metadata": {
        "id": "tVz3CdkwWfO_"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "y_pred = model.predict([10])\n",
        "y_pred"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "YplQwi81T3Vn",
        "outputId": "398fc8f3-17d3-4868-8fb7-6b047439ef28"
      },
      "execution_count": 15,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "array([[19.11774]], dtype=float32)"
            ]
          },
          "metadata": {},
          "execution_count": 15
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        ""
      ],
      "metadata": {
        "id": "6awKG_KsU1B6"
      },
      "execution_count": null,
      "outputs": []
    }
  ]
}
